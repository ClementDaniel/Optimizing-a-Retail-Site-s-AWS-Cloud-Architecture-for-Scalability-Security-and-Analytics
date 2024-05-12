# Optimizing-a-Retail-Site-s-AWS-Cloud-Architecture-for-Scalability-Security-and-Analytics

## Client Issues
- North American users experiencing slow load times may be the result of delayed content delivery to users who are located far away.
- DDoS Attack: It's possible that their current architecture isn't really well-suited for that kind of thing.
- API Oversubscription: In the event that API management is lacking, there may be a risk of API overloading.
- The intricate analytical queries: Because Aurora is a relational database, it might not be the ideal option for this level of analytical power.
- T2 instance intermittent availability problems: Because T2 instances are burstable by nature, there may be a performance deterioration during periods of strong demand.
- Issues before Cyber Monday and Black Friday: They will require a solution to manage periods of high traffic.

## Recommendations

#### Enhance the functionality and accessibility of your website.
- Replace the current T2 instances with M5, C5, or C6 instances, which are built specifically for heavy computing tasks and can handle large volumes of traffic.
- In order to increase performance during peak hours and reduce expenses during low-traffic periods, implement auto scaling to automatically modify instance count based on traffic demand.
- Distribute traffic among instances and availability zones using Elastic Load Balancer (ELB).
- Put resources closer to users in our AWS Region in North America.-west-2 or -east-1

#### Enhanced security and defence against DDoS assaults

- Utilise the managed DDoS protection solution AWS Shield to offer detection and mitigation of these attacks.
- In extreme circumstances, this can also entail setting up AWS WAF to defend the web application from DDoS assaults and to thwart malevolent bots that try to scrape your media files. By filtering traffic according to previously established rules, WAF prevents suspicious activity.
- Identity and Access Management, Implement least-privilege access to your resources, review and strengthen your IAM policies, and take precautions to prevent unauthorised access and any security breaches.

#### Apply API Management 
- To administer the APIs, use the API Gateway. To manage access and prevent oversubscription, the API Gateway has throttling, authentication, and authorization features.

#### Enhance the performance of the database
- Consider moving to an Aurora Serverless instance or upgrading to the next instance type.
- Set up a database cache using ElastiCache.

#### Create complex analytical queries
- We can explore moving the complex analytics workloads from Aurora to Amazon Redshift since it is fully managed and built to handle even the most demanding large-scale analytic workloads.
- Create cloud-based, next-generation business intelligence by utilising Amazon QuickSight.

#### Delivery of material and media files
- For local caching of static content, make use of a content delivery network like Amazon CloudFront in North America. This would reduce both the latency experienced by users and the loading times of websites.
- Turn on AWS S3 Transfer Acceleration to increase file transfer efficiency.

#### Monitoring
- Turn on CloudTrail to record user activities and API calls. To keep an eye on resource utilisation and spot any bottlenecks, use CloudWatch.This may optimise their infrastructure and troubleshoot performance difficulties with this assistance.

#### Load Testing
- Regular load tests: These simulate peak traffic to possibly identify some bottlenecks in architecture ahead of Black Friday and Cyber Monday.

## Desgin Implementation 
![Solution improve](https://github.com/ClementDaniel/Optimizing-a-Retail-Site-s-AWS-Cloud-Architecture-for-Scalability-Security-and-Analytics/assets/96403532/67bdfff1-4f78-4d46-967c-e1ce1247a7bb)

