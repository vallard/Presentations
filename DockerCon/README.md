#Dockercon 

## Day 1

### Netflix  - Titan

NoOps: You build it, you run it.  Every engineer is on pager duty. 

The operational benefits of a PaaS without the dilemmas of sandboxing technologies. 

* Don't want to limit
* people were writing their own workflow systems. 

Consistent Tooling and operational control plane for SREs across all 
technology stacks.  

Everybody seems to run private registers.  E.g: not using Docker paid
for registries. 

Auto scaling groups are harder to adopt for event based
orchestration systems.  

why docker:
* Process isolation
* immutable deployment artifacts
* ability to package dependencies. 
* tooling around the runtime for building and deploying
* scalable distribution of binaries across clusters.
* Netflix didn't build on top of cgroups, lxc, cause docker filled the gap. 
* Lots of training on how to make dockerfiles. 

### Shopify

Resiliency is the most importent: 
  * Build reliable service out of non-reliable components. 
Read: "Release it!" pragmatic bookshelf. 
Little's law: As response time goes up, throughput goes down. 

#### Service Discovery
Where is the infrastructure source of truth.  Store the state of 
the infrastructure.  

Discovery Backbone properties. 
* is this global or regional? 
* no single point of failure.  
* Stale reads better than no reads. 
* Reads orders of magnitudes bigger than writes. 
* What can you use? 
  * Eureka, Consul, Zookeper
  * Use Pure DNS for as long as you can!

Pressing issue: Global events.  Orchistrating data center failovers. 
* Too many sources of truth. 
* need more than DNS.  
* Zookeeper has been used for a long time by Netflix, and others. 
  * Can't slam DNS on it. 
  * operational burden. 
  * 

