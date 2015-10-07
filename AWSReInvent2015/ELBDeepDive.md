# ELB Deep Dive and Best Practices (Tues Oct 7, 2015: 1:30PM)
### Colm MacCarthaigh

I got in late cause the session was packed. 

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

