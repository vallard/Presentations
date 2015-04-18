# A Practical Introduction to DevOps Practices and Tools
* Chris Jackson - Distinguished Systems Engineer
* Vallard Benincosa - Application Delivery Architect
* BRKCLD-1003

## DevOps is So Hot Right now (situation)
* Mugatu Picture
  * Developers have won
  * Open Source and DevOps aren't mandatory, but neither is survival

## But we're not doing it (Concerns / Implications)
* Show someone worried
  * "I don't want to be a programmer"
  * "I'll be out of a job"
  * No budget this year, all to lines of business.

## But you can (Position / Action / Benefit)
* Don't be afraid
  * Many think you have to be a programmer, when the reality is "Not really"
* You'll understand what all these tools are. 
* Benefit: All Kinds of stuff

## Agenda
* Defining DevOps and why we use it
* Tools 
* Practical Examples 

## Defining DevOps
* Industry
* Who Does it where
* Why they do it. 


### Industry
* Bi-Modal IT
* Developer Changes
* What DevOps is now

#### Bi-Modal IT
* Lydia Leong
* 90% percent fail: Old tools repurposed isn't working
* Lines of business dismissing IT

#### The rise of the tester
* TDD 
* Rubber Chicken story

#### What DevOps is Now
* Gene Kim "The Phoenix Project": "Set of cultural norms and technical practices that enable this fast flow of work from dev through test through operations while preserving word class reliability."

### Who does it
* Unicorns: Facebook, Google, Usual Suspects
* Horses: Macy's, you can do it too!

### Why do it
* Most people are wrong.  
* Most features don't lead to more profits. 
* HiPPO
* "Instead of trying to get better at predicting the future, we should 
improve our ability to adapt rapidly and effectively to new information"
-- Lean Enterprise

### The Mindset
* "Do the least amount of work to deliver the expected outcome"

### How we Do it
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

### Continuous Integration
"The practice of working in small batches and using automated tests to 
detect and reject changes that introduce a regression."

How do we know if we're doing it?
* Are developers checking into the trunk at least once a day?
* Does every check in kick off a build process that runs automatic tests?
* When the build and test process fails, does the team fix within a few
minutes?

Source: Lean Enterprise: How High performance organizations innovate at 
scale: Chapter 8
