# AWS re:Invent 2018: Architecture Patterns for Multi-Region Active-Active Applications (ARC209-R2)

* [Original video](https://www.youtube.com/watch?v=2e29I3dA8o4&ab_channel=AmazonWebServices)
* [Blog post](https://aws.amazon.com/blogs/architecture/disaster-recovery-dr-architecture-on-aws-part-iv-multi-site-active-active/)


## Definitions
1. Failover - a procedure by which a system automatically transfers control to a duplicate system when it detects a fault or failure.
2. Multi-region active-active - 2+ active full stacks in different AWS regions.

## Why NOT multi-region?
1. Data replication lag.
2. Testing complexity (dedicated teaming working fulltime).
3. Overall complexity and cost.

## Why multi-region?
1. Business continuity/disaster recovery.   
![image](https://user-images.githubusercontent.com/11683340/179389706-018f5c3b-0c91-4c77-935b-9c26849f35ca.png)
2. Avoid latency for geographically distributed customer base.   
![image](https://user-images.githubusercontent.com/11683340/179389747-3b29a3a4-aaa1-43b1-a261-6ba57b9eb3d4.png)    
❗Validate that latency really matters before doing this.
3. Meet legal and data regulatory compliance

## Does it need to be multi-region?
![image](https://user-images.githubusercontent.com/11683340/179389999-71cdc658-0e2f-4d87-ba29-887a49321329.png)
❗Multi-region is not black-and-white. There are different options.

## Business continuity 
![image](https://user-images.githubusercontent.com/11683340/179390082-0c65c55d-ee97-4ced-8db8-1e08e78d1fdd.png)

## Multi-region Strategies

| Strategy          | Data loss time     | Recovery time     |
|-------------------|--------------------|-------------------|
| Backup & restore  | hours              | hours             |
| Pilot light       | minutes            | minutes           |
| Warn standby      | seconds            | seconds           |
| Active-active     | 0                  | 0                 |

### Backup & Restore
![image](https://user-images.githubusercontent.com/11683340/179390188-7ab8c116-852e-4b99-a0ec-6a5354daa8a7.png)

### Pilot Light
![image](https://user-images.githubusercontent.com/11683340/179390209-552dd12a-a31a-48c8-8c81-c447ecb0f4e2.png)

### Warm Standby
![image](https://user-images.githubusercontent.com/11683340/179390257-aedff5c5-53ce-417e-bf88-08d7c707ff18.png)


## Active-Active Design Patterns
### Read local, write global
![image](https://user-images.githubusercontent.com/11683340/179390986-dcd7989d-a8a5-4d53-9115-129502cce05e.png)

Use when read-write ratio is 99%, e.g. registration, authorization systems.
Do that if you can.

### Read local, write partitioned
![image](https://user-images.githubusercontent.com/11683340/179391085-dc2d32a3-70dc-41f7-a518-4edde09b5631.png)

Use when read-write ratio is 50%.
Do that if you have to.

### Read load, write local (! anti-pattern)
![image](https://user-images.githubusercontent.com/11683340/179391418-352e001a-fbf5-4a82-8342-f4e9076c2c5c.png)

Do that if you dont have any other choices. 

## Multi-region Implementation Tools
### S3
* Availability Zones
* S3 cross-region replication

### EBS
* Snapshots saved cross region

### DynamoDB Global Tables
* Fully managed, multi-master, multi-region database

### RDS and Aurora

## Multi-region Operations (Networking, Security)

### VPC
1. Inter-Region VPC Peering (single VCP across multiple regions) via AWS backbone
2. Multi-VPC connectivity (multiple VCPs across multiple regions)

### Route 53
1. Latency-based routing
2. Geolocation routing
3. DNS failover

### Network Load Balancer (NLB)
1. NLB + Inter-Region VPC Peering

### Global Accelerator
1. Single global (anycast) IP

## Managing Multi-region Active-active Environment
### CloudFormation StackSets
### Aws Config rules
![image](https://user-images.githubusercontent.com/11683340/180622926-b36589ed-2f3e-4728-8bcb-c5d376baf38f.png)


## Test Failure Modes
