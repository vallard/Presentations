# A Practical Introduction to DevOps Practices and Tools
* Chris Jackson - Distinguished Systems Engineer
* Vallard Benincosa - Application Delivery Architect
* BRKCLD-1003

## Intro
### DevOps... So Hot Right now (situation)
![Devops... so hot right now](http://gabrielchapman.com/wp-content/uploads/2015/02/DevOps.jpg "Devops is so hot right now")
  * Developers have won
  * Open Source and DevOps aren't mandatory, but neither is survival

### But we're not doing it. (Concerns / Implications)
![Is everyone hanging out without me?]( http://ecx.images-amazon.com/images/I/51O5o-cFKQL._SY344_BO1,204,203,200_.jpg "Are we missing out on what the cool kids are doing?")
* Is everyone hanging out without me?
  * "I don't want to be a programmer"
  * "I'll be out of a job"
  * No budget this year, all to lines of business.

### But we can. (Position / Action / Benefit)
![Be the walrus]( http://bunchfamily.ca/wp-content/uploads/2013/04/Broderick-huh.jpg )
![Be the walrus]( https://hughdellar.files.wordpress.com/2012/09/thebeatlesthewalruswasntpaul.jpg )
* But we can be the Walrus
  * Many think you have to be a programmer, when the reality is "Not really"
* You'll understand what all these tools are. 
* Benefit: All Kinds of stuff

## Agenda
* Part 1: Defining DevOps and why we use it
* Part 2: Tools 
* Part 3: Practical Examples 

## Part 1: Defining DevOps
* Industry
* Who Does it where
* Why they do it. 

### Industry
* Bi-Modal IT
* Developer Changes
* What DevOps is now
* How we do it

#### Bi-Modal IT
* Lydia Leong
* 90% percent fail: Old tools repurposed isn't working
* Lines of business dismissing IT

#### Changes in Development
* TDD 
* Rubber Chicken story

#### What DevOps is Now
* Gene Kim "The Phoenix Project": "Set of cultural norms and technical practices that enable this fast flow of work from dev through test through operations while preserving word class reliability."

#### How we do it 
* Who does it
* Why we do it
* The mindset
* Breaking things up
* Continuous Integration

##### Who does it
* Unicorns: Facebook, Google, Usual Suspects
* Horses: Macy's, you can do it too!

##### Why do it
* Most people are wrong.  
* Most features don't lead to more profits. 
* HiPPO
* "Instead of trying to get better at predicting the future, we should 
improve our ability to adapt rapidly and effectively to new information"
-- Lean Enterprise

##### The Mindset
* "Do the least amount of work to deliver the expected outcome"
* Don't forget: It's the application

##### Breaking things up
* Make Engineering safe and economic by working in small batches
  * Shorter Lead times
  * Higher quality work
* Requirements
  * Safe: Deployment pipeline
  * Quick: How long does it take to get a single line of code to your customers?
  * Sustainable: "If it hurts, do it more often" eg: Testing, Integration
  * Story of customer who does updates once a year.  Yikes! The night of hell

Source: Lean Enterprise: How High performance organizations innovate at 
scale: Chapter 8

##### Continuous Integration
"The practice of working in small batches and using automated tests to 
detect and reject changes that introduce a regression."

How do we know if we're doing it?
* Are developers checking into the trunk at least once a day?
* Does every check in kick off a build process that runs automatic tests?
* When the build and test process fails, does the team fix within a few
minutes?

Source: Lean Enterprise: How High performance organizations innovate at 
scale: Chapter 8


### End of Part 1:
Map of the big picture:
Continuous Delivery
Continuous Integration
DevOps
Configuration Management


## Part 2: Look at the Tools
* Source Code Repositories
* Automated Build Processes 
* Collaboration Tools
* Configuration Management Tools

### Source Code Repositories
* Git
* Docker Registry

#### Git
* Git / GitLab
* Linus Torvalds 

Why git won: it made branching simple
Why Github shutdown Google Code

#### Containers
* Why Docker
* Dockerhub , Registry 2.0
* Google Container Registry? (https://cloud.google.com/tools/container-registry/) - gcr.io/myproj

### Automated Build Processes
* Jenkins
* Travis CI
* Team City

### Collaboration Tools
* Gerrit
* trello 
* hipchat

### Configuration management tools (What you thought this talk was about)
* Audience Poll:  What are you using?
  * Puppet
  * Chef
  * Ansible
  * Salt
  * Terraform
  * CloudFormation
  * Heat

(Packer, Consul, ...)

### Tools for users
* Vagrant
* boot2docker

## Part 3:  Architectures
* Demo of Lawngnomed.com
  * Using COPC APIs with Ansible, Jenkins, Docker, all internal

* Yelp
  * Building System Packages (Evan Krall) @meatmanek
    * Build a system package
    * Make it available on internal package repo
  https://vimeo.com/112725792

* Example on AWS

* Example with UCS Director?  Intercloud Fabric?

## Closing
Hopefully in this talk you gained:

* An Understanding of the state of the industry and why this came about
* An Understanding of the tools
* How they work together

