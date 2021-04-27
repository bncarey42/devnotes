# AWS Regions
Regions are sets of data centers grouped by geographical places

ex: `us-east-2 (US East (Ohio))`

### Availability Zones

One or more discrete data centers geographically isolated connected by high bandwidth low latency networks

usually 3 zones per region (min 2, max 6)

EX: 

<table><tbody><tr><td colspan="3">AWS Region: Sydney: ap-southeast-2</td></tr><tr><td>ap-southeast-2a</td><td>ap-southeast-2b</td><td>ap-southeast-2c</td></tr></tbody></table>

![](AWS%20Regions/image.png)

NOTE: that some services (like EC2) are region specific while others are global (like IAM)

Global Infrastructure: [`https://aws.amazon.com/about-aws/global-infrastructure`](https://aws.amazon.com/about-aws/global-infrastructure)

high level description of AWS functionality, AZ Map, and service statu