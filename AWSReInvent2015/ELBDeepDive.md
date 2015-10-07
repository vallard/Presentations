# ELB Deep Dive and Best Practices (Tues Oct 7, 2015: 1:30PM)
### Colm MacCarthaigh

I got in late cause the session was packed. 


![Session 3](./images/session3.jpg)

* Lots of theory, very little practical for the first 30 min. 
* ELB manages the SSL for you. (Huge!)
* Not a very engaging session for me. 

## SSL/TLS cipuer suites
* Prefer AES over 3DES over RC4
* Prefer GCM over CBC + HMAC
* Legacy clients can cause compatibility issues.  
* ELB defaults strike a balance
* Access log gap analysis
* Recommend ELBSecurityPolicy-2015-05

Every request is logged. Partner integration with splunk, sumologic, loggly. 
## ELB and security compartmentalization

* Public subnet ELBs but you can use ELB on private subnet. 

## Scalability 
```
Latency = Load / Throughput
```
Most request are small and take a small number of milliseconds. 
So we have small requests waiting for the large requests to get the average
wait time.  (Negative exponential curve)

ELB's own scaling is a mix of premptive, based on the instance capacity you add, and reactive, based on the load you recieve. 
