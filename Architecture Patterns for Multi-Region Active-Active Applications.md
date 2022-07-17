# AWS re:Invent 2018: Architecture Patterns for Multi-Region Active-Active Applications (ARC209-R2)
https://www.youtube.com/watch?v=2e29I3dA8o4&ab_channel=AmazonWebServices

## Definitions
1. Failover - a procedure by which a system automatically transfers control to a duplicate system when it detects a fault or failure.
2. Multi-region active-active - 2+ active full stacks in different AWS regions.

## Why NOT multi-region?
1. Data replication lag.
2. Testing complexity (dedicted teaming working fulltime).
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

### Strategies

| Strategy          | Data loss time     | Recovery time     |
|-------------------|--------------------|-------------------|
| Backup & restore  | hours              | hours             |
| Pilot light       | minutes            | minutes           |
| Warn standby      | subseconds         | subseconds        |

#### Backup & Restore
Data loss ~ a day
Recovering time ~ hours

![image](https://user-images.githubusercontent.com/11683340/179390188-7ab8c116-852e-4b99-a0ec-6a5354daa8a7.png)

#### Pilot Light
Data loss ~ minutes
Recovering time ~ an hour
![image](https://user-images.githubusercontent.com/11683340/179390209-552dd12a-a31a-48c8-8c81-c447ecb0f4e2.png)

#### Warm Standby
Data loass ~ subseconds
Recovery time ~ subseconds
![image](https://user-images.githubusercontent.com/11683340/179390257-aedff5c5-53ce-417e-bf88-08d7c707ff18.png)


#### Active-Active

### How do I re-design
