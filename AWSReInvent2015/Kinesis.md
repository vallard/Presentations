# Kinesis Deep Dive and Best Practices

## What to expect
* System Overview
  * Streams (this session)
  * Firehose (available)
  * analytics (announced)
* 10 things to know
  * ingestion models
  * streaming applications with Kinesis client library
* AdRoll: Re-architecting our real-time data pipeline
  * Nick Barrash, SDE AdRoll

## Kinesis Streams
* Easy Admin
* BUild real-time applications
* low cost

## Kinesis Streams
All data puts into a replayable ordered stream of events emerges.  Replicated across three regions.  

## Putting Data into Kinesis
* Provision stream 
* Each Shard: 1MB put, 2MB Read
* PUT API call is used to add data. 
* Size of a single record can be no greater than 1MB. 
  * usuallyt hey are small
* Partition Key is put into the Put request. 

## Ingest Models
* Managed Buffer
  * producers create a reliable buffer
* Streaming Map-Reduce
  * leverage partition keys as a natural way to aggregate data

## Put data
High frequency best is PutRecords: supports 500 records in a single call. 

Successful response gives a shard ID and Sequence Number. 

Each putRecords ENtry with ErrorCode != NULL should be added to a subsequent request. 

## Kinesis producer library

Use the [producer library](https://github.com/awslabs/amazon-kinesis-producer) and build into the application.  

