# AWS IoT DeepDive: Securely Building, Privisioning, and Using THings with AWS IoT
#### Eric Brandwine

Everything is becoming connected, but that doesn't mean they are becoming smarter. 

Simple goal: secure connections between devices.

We sometimes think: Our data is not sensitve, but that is because people think people to machine interactions.  Security is more important when doing thing to thing communication. 

A rogue actor that feeds fraudulent data into the system can have major consequences. 

Anybody can snoop and read MQTT protocols.

## Mutual Auth TLS

* person shopping goes to Amazon.com.  The person then gets a public TLS certificate. 

* device talks to the IoT protocol.  Server presents certificate and is authenticated.  Client will also have a certificate sent to AWS. 

## AWS-Generated Keypair
* CreateKeysANdCertificate()
* user gets this key and cert and puts it on the 'thing'

```
aws iot create-keys-and-certificate --set-as-active
```

The downside of AWS-Generated Keypair is that it moves across the network.  AWS doesn't ever write it to disk. 

* AWS has its own CA
* CreateCertificateFromCSR(CSR)

```
openssl genrsa -out ThingKeypair.pem 2048
oepnssl req -new -key ThingKeypair.pem -out Thing.csr
```

```
aws iot create-certificate-from-csr \
--certificate-sign...
```
now we have to remove permissions

```
cmod 400 ThingKeypair.pem; ls -l ThingKeypair.pem
```

## Private Key Protection - Software Threats
* chroot
* SELinux
* OTP Fuses
## Hardware Threats
* TPMs
* SmartCards
* Locks and Boxes
* FIPS-Style hardware
```
aws iot list-certificates
aws iot -udate-certiciate --certificate-id "fasdfsadfasdf" --new-status REVOKED
```
REVOKED command is not REVOKABLE :-)

## Manging Things

by setting policies users can manage certificate in the AWS console. 

## Identity Federation

people are bad at using passwords.  Smart cards work to do this with a set of keys. This is already a service in AWS and this now works in IoT. 



