# Internet of Things application

## Cognito

We setup a cognito bucket 

### Cognito Lab

* Create a new cognito pool. 


## Kinesis

writers: 1 MB/s
readers: 2 MB/s

Shards can be created to handle more data.  

We will use the cognito ID as the shard ID. 

Where Kinesis is different than a queue, multiple consumers and can
grab at any time whereas normal queues only have one consumer.  The 
multiple consumers have their own pointers to where they are in the 

Shards scale elastically without losing sequencing.  Data in each
shard is available for 24 hours. 

### Kinesis Lab

* Create a Stream
* Create AWS Lambda Roles for all the services 
* Use CloudFormation to define more roles. 
  * [Sample Cloud Formation ](http://bootcamp2015-mobile-iot.s3.amazonaws.com/bundle/Desktop/Bootcamp2015- CognitoAuthenticatedPolicies-CloudFormation.template)

### Edison 

Edison is an Intel system on a chip. 

#### Lab

In this lab we connect the Edison and run a node.js app that sends stuff up to AWS. 
* UUID
* root password:  edison2015
* edit: /etc/bootcamp2015-config.js

Connect: ```screen /dev/cu.usbserial-A402IX8E 115200 -L```

Restart the lab: 
* ```systemctl restart bootcamp-register.service```

Verify bluetooth is running: 


* ```hcitool lescan```
* ```hciconfig hci lestats```



### BLE - Bluetooth low energy

* RSSI - how far apart signals are by noise of the signal. 
* Uses the Kalman Filter. Smooths out the raw RSSI signal . 
* We live in an uncalibrated environment called the world. 
* 1 meter away -59 would be the signal. 

Node.js libraries fro BLE: 
* Bleno: Advertises existence
* Noble: Detect

#### Lab 4: Test

```
cd ~/labs/
node test-ble-to-kinesis.js
```

### AWS Lambda

* zero-administration
* connective tissue to other AWS services
* Syncronis web services or Async
* Can be triggered using SNS notifications, Cognito, Kinesis, etc. 


### Anazon DynamoDB

* Managed NoSQL in the Cloud
* schema-less data model
* fully native with IAM. 
* Hash Key is the primary record.  

#### Lab 5: AWS Lambda Function & DynamoDB

* Create a lambda event selecting Kinsis Process Record
* Configure it to grab the latest in starting position
* [Provisioned Throughput](http://docs.aws.amazon.com/amazondynamodb/latest/developerguide/ProvisionedThroughputIntro.html)

### Amazon SQS

* Reliable messages stored redundantly
* Main differences: multiple subscribers but first one to the message gets it
and deletes it and it is gone forever.  Kinesis allows for 24 hours
* Simple: 5 API calls. 
* VisibilityTimeout if process doesn't delete it, then AWS assumes app died. 

#### MQTT
* MQ Telemetry Transport
  Designed for messages exchange between contrained devices and low-bandwidth, high-latency or unreliable networks.  

* Simple & Lightweight
  Uses TCP, long-lived connection to an MQTT broker.  

* Using the mqtt node.js library. 

Each device subscribes to its own message broker. Ignore the messages you send to yourself. 

### Amazon SNS

Coordinates and manages the delivery or sending of messages to subscribing endpoints or clients. 

* SNS is point-to-point or one to many in fan-out. 
* Solves a multiple devices problem.  Send a single notification to multiple devices. 

1. Bob presses notification, sends to SQS
2. Goes to his IOT
3. MQTT to secondary device. 
4. Up to SNS, Lambda, SNS to receiver user. 

Two SNS steps in step 4 are different topics. 

Real life use case: communication when near by. 

### Amazon API Gateway

* Performance at any scale
* Run your APIs without Servers
* Deploy, Generate  SDKs & Monitor your API!

* Resource is a logical entity that can be accessed by a resource path. ```http://my.api.com/login```
* Methods: resource path and an HTTP verb: GET, POST, DELETE
* Models: Defines the format, also known as the schema or shape. 
