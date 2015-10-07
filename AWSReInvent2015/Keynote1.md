# Keynote: Wed Oct 7, 2015 with Andy Jassey

## New Announcements: 

* [Amazon QuickStart](https://aws.amazon.com/quickstart/)
* [Amazon Snowball](http://techcrunch.com/2015/10/07/amazon-launches-snowball-a-rugged-storage-appliance-for-importing-data-to-aws-by-fedex/) (This was pretty cool!)
* [New RDS backend with MariaDB](https://aws.amazon.com/blogs/aws/amazon-rds-update-mariadb-is-now-available/)
* [AWS DMS: Database Migration Service](https://aws.amazon.com/dms/)
* Schema Conversion Tool (part of DMS)
* [Web Application Firewall (WAF)](https://aws.amazon.com/waf/) (Announced earlier this week)
* [AWS Config Rules](https://aws.amazon.com/blogs/aws/aws-config-rules-dynamic-compliance-checking-for-cloud-resources/) - Set compliance rules for resources with triggers
* [Amazon Inspector](https://aws.amazon.com/blogs/aws/amazon-inspector-automated-security-assessment-service/) - Detect and remediate security issues early and often

Vallard Take: Snowball, QuickStart, Datbase migration tools, and Config rules are super cool.  Amazon is taking swings at Oracle here in a big way. 

## Introduction

95% increase YoY of Instance usage. 
120% increase YoY of S3 usage. 
127% increase YoY in database services.

$7.3B run rate in Q2 2015 (doubled almost from last year)

81% YoY growth.  Fastest growing multibillion ent tech company. 

more compute capacity than largest 10 competitors combined. 

* Most successful startups use AWS
* Every vertical imaginable
* Large public sector business

## Ecosystem
* System Integrators super important to help customers move
* ISV partners have migrated apps to AWS.  Large environment. 
* AWS marketplace: 2300 listings, 800 ISVs, 143M EC2 Instance Hours

## Why are customers miving to the cloud so fast? 
* move capital to variable cost is better. 
* agility 
* lower variable expense than could be achieved on their own. 
* Remove undifferentiated heavy lifting

What makes them passionate about the cloud? 
* Freedom and controlling your own destiny. 
* builders not blocked. Developers didn't get into CS to do the same thing
* Helps CIOs and developers be creative. 

## Seven Basic Freedoms

### 1. Freedom to build, unfettered
  * removes barriers: quick to provision + robust infra technology platform.
  * lots of storage services, database services, analytics services...
  * deployment: containers, lambda, notifications, transcoding, messaging. 
  * Here, Andy tries to list every single service
  * A lot more features in those services:  
    * compute: I/O , memory, CPU optimized. 
    * database: aurora, sql, 
    * encryption
    * access control: during timeframe, any time. 
  * "IT organizations cannot treat cloud IaaS providers like commodities" - Lydia Leong

### 2. Freedom to get the real value from your data
  * Companies didn't keep the amount of data they wanted to keep. 
  * Core components for big data workloads
  * 70% savings from doing big data on site? 
  * Why is most of the company left in the dark? 
    * Cognos: $150 - $250 / month (3 year TCO) more expensive. 
  * AWS QuickSight Announced. 
    * first visualization in 60 seconds. 
    * SPICE: fast in memory query engine.
    * beautiful visualization
    * 1/10th the cost.  

### 3. Freedom to get your data into or out of the cloud easily
  * Direct upload or Direct Connect (Private Connection)
  * Real Time streaming: lots of devices everywhere constantly transmitting. 
  * Kinesis Streams: Processing of realtime streaming data.  
  * New Service:  Amazon Kinesis Firehose
    * allows you to take streaming applications and move to S3 or Redshift
    * automatic scaling
    * encrypt with keys on the way in and decrypted when needed. 
  * Migrating large volumes of data to AWS is still a problem.   
    * would take 100 days to load 100TB in the cloud with Gbps link. 
    * never underestimate the bandwidth of a FedEx truck
    * import / export service was built to handle this. 
      * you have to buy disks yourself. 
      * encrypt or decrypt?  
  * Amazon Snowball Container
    * Encrypts data, fast way of getting data into the cloud. 
    
### 4. Freedom from bad (Database) relationships
  * Database space has been the slowest to move more towards cloud. 
  * Expensive, Proprietary, Lockin, Punitive licensing. 
  * One reason Amazon Aurora was announced.  Supposed to replace Oracle. 
  * 1/10th of cost of old guard database solutions. 
  * Aurora is the fastest growing AWS service. Looking for more freedom.
  * More OpenSource options:  
    * MariaDB Engine added to RDS. 
  * Migrate databases to the cloud: 
    * AWS Database Migration services 
    * $3 to convert TB database
    * AWS schema conversion Tool 
      * Converts triggers, functions 

###  5. Freedom to Migrate
Over the last 18 months conversation: "I get benefits, but need help moving"
* most people move in phases: 
  * Dev/Test
  * Websites/Analytics/Mobile
  * Mission Critical
  * Data Center Migration
Johnson/Johnson 120 apps on AWS to make their "Borderless Data Center"  
 

### 6. Freedom to secure your cake and eat it too.

Question most Enterprises struggle with: 
_How much freedom? Let builders move quickly or keep them in._ 

* AWS has a ton of certifications: ISO 9001, HiPPA, PCI compliance
* Broad set of services to secure applications in the cloud
* Cloud Trail and resource auditing with AWS Config

AWS Config Rules
* Suppose we say all EBS volumes should be encrypted
* Config will monitor and send scripts or emails 
* All instances must be launched within a VPC - terminate if not done. 
* Instances must be tagged with Environment Type - action: page developer

Amazon Inspector: Automate Security assessment service that finds compliance issues. 
* Full audit trails

### 7. Freedom to Say Yes. 

BS marketing fluff to just say that people can move to the cloud and that
AWS is good. 


## Guest Speakers 

### Rob Alexander - CIO: Capital One
* largest credit card companies: 70 million accounts. 
* digital is the new bank branch with mobile being the preferred channel. 

Presentation seems more of a way to attract developers to come work for 
them.  

* human centered design


### QuickSite  Demo with Dr. Wood. 
* Discover Data Sources Automatically to make easy to use. 
  * Inspects data types and relationships. 
  * selects the best visualization using AutoGraph. 
* Analysis SPICE: 
  * Super-fast parallel in-memory computation engine
  * Extensible for customers with partners able to plugin: tableau. 
* Share and Collaborate Using Analysis
  * mobile apps with custom graphs. 

### Bill Vass, VP AWS storage services.
Breakout on Amazon Snowball
* Get 250 PBS to AWS.
* Can download a PB in 15 hours. 
* Don't have to mess with boxes or shipping labels. 
* 1/5 the cost of shipping over the network. 
* Automatically convert from Fileservices to Object storage. 
* Go to console order just like Amazon stuff.  
* 10 snowballs gives a 100Gb of bandwidth. 
* $200 per job (50 TB to ship to AWS)

### Jim Fowler - CIO of GE

Talked about how industrials need to become digital companies and use
hybrid cloud. 

In 2020 $15 billion in GE revenue will come from software. 
* 9,000 applications used
* 140 year old company

### Omar from Accenture

Introducting: Accenture AWS business Group

Takes the consulting company and focuses exclusively on AWS. 

### Jorge Ortiz - Manager Infrastructure - Stripe

"If you empower developers they will do great things"

Stripe is for developers to integrate payments into their applications. 

* World-class infrastructure with AWS
* seamless scaling
* developer productivity

"Our customers don't worry about payments, we don't worry about infrastructure"

### Joe Enzerillo EVP and CTO at MLB

Cory and I walked out at this point, but it was really cool to see how 
MLB has transformed to a digital company. 
