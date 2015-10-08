# AWS Cloud Formation Best Pratices

_Session was super crowded and I didnt' get in until it was like half way over_

First Demo was super good with [Stack Designer](http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/working-with-templates-cfn-designer-walkthrough-createbasicwebserver.html).  

## New services added

* Lambda
* Spotfleet (you give size)
* Aurora
* MariaDB
* SimpleAd
* CodeDeploy
* workSpaces

## Cloud formation in organizations
- all resources tagged automatically and then cost seen with stack explorer.
- notifications if this gets expensive
- integrated with cloud trail so you see everything.

## Advanced concepts

Language features
Ref - get ID of resources.

## Extend cloud formation
- non AWS resources.
Events are created when stack is deployed. SNS topic can be created and then worker can deploy external tool.

## Custom resources
ServiceToken will send SNS message to external resource. If it fails the entire stack will fail.

## Lambda backed custom resources.

## Re-using templates acreoss AWS Regions
* different environmental regional differences (EC2 image Ids)
* Endpoint Names
* Amazon Resource Names

### Use pseudo-parameters to retrieve environmental data. 
* account Id
* Region 
* Stack Name and Id

### Use Mapping to find Resources.

```
Fn::FindInMap":  ...
```
Mappings has a RegionalConfig and then finds 

### Re-usable Templates with Conditionals

This is useful to support AWS regions that may have VPCs or be in EC2 classic. 

```javascript
"Conditions" : {
  "Is-EC2-VPC" : { "Fn::Or" : [
    {"Fn::Equals" : [
      {Ref : AWS::Region },
      "eu-central-1" ] }
    {"Fn::Equals" : [
      {Ref : AWS::Region },
      "eu-central-1" ] }
      ]
  } 
}
```

## Conclusion

* CloudFormation Designer overview
* In your organization
* Advanced Concepts
* Best Practices.
