Public Cloud Providers (AWS)


`AWS fundamentals`

Key components (EC2, AMI,  IAM, Storages, Queues etc.)
EC2 instance types and scaling
Avaialbility Zones and Regions


*** What are  AWS key components and what goal they serve?
What is VPC? (ask few questions on key components)
What instance types do you know and what for those are optimizrrd?
How to scale EC2 instances?
Availability zones and regions

`Networking`
Virtual Private Cloud and Subnets, SG vs ACL  
Route53, DirectConnect, CloudFront, VPC endpoints
LoadBalancing (ELB, ALB), ApiGateway
Peering, NAT, VPN

* What are the properties of default VPC?
How to open port on the EC2 for connection?
How to allow connection from EC2 to RDS instance?

** How to allow trafic of different VPCs?
What is VPC peering and what topology does it support? 
Types of LoadBalancers, what is the difference between V4/V7?
What is the difference between CNAME and A record in route53?
What Route53 routing policy should be used to split trafic in exact 
proportion of 20%/80% traffic between 2 regions?

*** How integrate DC and AWS network and replicate data/ precache data on AWS/DC side?
How to guarantee network connnection to services over private network (no public) ?

Serverless

*** AWS Lambda deployment
AWS Lambda limitations 
AWS Lambda retry policies

**** Securitty
Cold start and scaling
Execution model
When to use


* How AWS Labmda is deployed and how it can be auttomated?
What frameworks can be used with AWS Lambda?
What  limitations do you know? (e.g. time)

** How retries are working in AWS Labmda and what those do depend on?
Please list best practicies to write lambda function

**** Security practicies
What is cold start and how to deal with?
How AWS Lambda functions are executed and scaled?
What may affect AWS Lambda performance?
Please define pros and cons of going serverlesss and use cases when thiis will not work


`Compute`
*** VM: EC2 (machine types/spot instances use cases, cloud init), ElasticBeanStalk
**** Managed containers services: EKS, ECS, ECR


*** What is AMI, how to use it?
How to add custom logic, packets installation on VM start?
How to configure scale up/down EC2 machines based on load/demand, what are the best practices, proactive scaling, etc?
What types of EC2 instances do you know (difference between on-demand/reserved/spot)?

**** EKS security and billing?
When to use EKS, ECS, ECR?
ElasticBeanStalk deployement types (all-at-once/rolling/with batch/immutable) use cases differences?

`Storages & Databases`

* Object storage: S3 classes, Lifecycle Rules, Access to static content, Access Control List, Token Access, Optimizations for highload
** Migrations: DB migration, Snowball, Storage Gateways
** Block strorage: EBS, EFS, RAIDs
** Managed DBs: RDS, Aurora, Redshift, DynamoDB, DAX, NeptuneDB, ElastiCache, ElasticSearch, DocumentDB


* Describe Data Consistent Model for AWS S3?
What storage types present in S3, what has the highest SLAs and HA?
How to implement static content hosting with S3(what is CORS)?

** What types of EBS exist, how to backup and restrore encrypted EBS in another region?
Bucket policies and Encryption types of S3 for transit and at rest, how to specify encryption type ?
How to transfer big ammounts of data from DC to Cloud?
What is the difference between instance store and EBS?
Describe LSI, GSI, how to design RCU/WCU?
Types of replicas supported for RDS, differences between them?
Describe supported Cache engines of ElasticCache and its use cases?
Difference beteeen Lazy loading and Write Throung Cache strategies?

`Messaging & Streaming`

* SQS, SNS, MQ, Pinpoint, 
** Kinesis, IoT MQTT Broker,  Dynamo streams
*** Scaling, Sharding, Integration with other services, limitations

* Difference between SNS & SQS?

** What is SQS extended clinet ?
How to consume same message from SQS by multiple consumers?
SQS: messages types, formats, limitations, delivery semantic, DLQ, ACKs, visibility timeout?
Does SQS supports ordering? what types of queues do you know?

*** Describe the difference of Aggregation and Collection for Kinesis Producer Library?
Kinesis usecases
Kinesis FanOut vs Standard consumer, sharding, limitations?

`Security & Ops`
* Organization/Account, IAM, SAML, STS, types of access, concept of roles, policeis, service accounts, MFA, permission types
* Shared security responsibility Model
* CloudWatch, CloudTrail, X-Ray 
** CLoudHSM, KMS, data encryption at rest and in transit, System manager Parameter Store, Cognito
** Opswork, CloudFormation

* What are best practices to apply role access to machines and on App level?
CodeDeploy difference in In-Place and Blue/Green deployments?

** How will you store CREDs on AWS?
What types of encryptions are supported to S3, how they are configured and used?

*** Describe difference between CloudHSM and KMS?
STS usage and flows?


`Services for Data-intensive apps`
**  IoT architecture and components 
** Athena,Redshift, Glue, QuickSight
**** Edge computing

** How to achieve High IO netwroking between EC2 intstances for data intensive distributed systems?
How you will design ETL processing on AWS?
Describe IoT platform componenets and integration?
AWS Glue: supported data formats, internal architecture, what is crawler, job, data catalog? 

*** GreenGrass, Edge computing?


`Best Practices (HA/DR/Billing) and Whitepapers`


https://docs.aws.amazon.com/prescriptive-guidance/latest/sql-server-ec2-ha-dr/options-considerations.html


Disaster recovery - аварийное восстановление
high availability - высокая доступность 

** Definitions of Fault Domain and Availability Group. Concepts of HA. Achieving 
Определение домена - сбоя и групп доступности.  Концепции высокой доступности.

HA for compute instances, storages, databases
Высокая доступность инстансов, хранилищ, баз данных 

** Types of DR, concepts of RPO and RTO
- Types of dsaster recovery
- Conceps of recover point object(RPO)
- Concepts of real-time operating system

`** AWS Well-Architected Framework`
The AWS Well-Architected Framework describes key concepts, design principle, and architectural best practices for designing and running workloads ih the cloud. By answering a few foundational questions, learn how well your architecture aligns with cloud best practices and gain guidance for maing improvements. By using the framework you will learn operational and architectural best practices for designing and opeating reliable,secure, efficient, cost-effective, and sustainable workloads in the cloud. It provides a way to consistently measure your opeations and architectures against best practices and identify areas for improvement. We believe that having Well-Architected workloads that are designed with operations in mind greatly increases the likehood of business success.
    - Operational Excellence
    - Security
    - Rellability
    - Performance Efficiency
    - Cost Optimization
    - Sustainability

## Operational Excellence Pillar
The operational excellence pillar focuses on running and
monitoring systems, and continually improving processes and
procedures. Key topics include automating changes,responsing to events, and defining standards to manage dayily operations.

## Security Pilar 
The security pilar focuses on protecting information and systems. 
Key topics include confidentiality and integrity of data,
managing user permissions, and establishing controls to detect security events.

## Reliability Pilar
The reliability pilar focuses on workloads performing their intended functions and how to recover quickly from failure to meet demands. Key
topics include destributed system design, recovery planning, and adopting to changing requirements.

## Performance Efficinency Pilar
The performance efficinecy pilar focuses on structured and streamlined allocation of IT and computing resources. Key topics include selecting resource types and size optimized for workload requirements, monitoring performance, and maintaining efficiency as business needs evolve.

## Cost Optimization Pilar
The cost optimization pillar focuses on avoing unnecessary costs.
Key topics include understanding spending over time and controlling fund allocation, selecting resources of the right type and quantity, and scaling to meet business needs without overspending.

## Sustainability (устойчивость) Pilar
The sustainability pilar focuses on minimizing the enviromental impacts of running cloud workloads. Key topics include a shared responsiblity model for sustainability, understaning impcat, and
maximizing utilization to monomize required resources and reduce downsteam impcats.


https://aws.amazon.com/architecture/well-architected/?wa-lens-whitepapers.sort-by=item.additionalFields.sortDate&wa-lens-whitepapers.sort-order=desc&wa-guidance-whitepapers.sort-by=item.additionalFields.sortDate&wa-guidance-whitepapers.sort-order=desc




*** Maximizing Value with AWS (cost optimization)

*** Data migration into AWS platform?
 Hybrid networking and architecture?
 Least priviledge security model, encryption in rest and transit for different services?

**** Performance optimizattion practicies
Cost optimization practicies
Discuss listed whiteparers 


AWS - Well - Architected:

Gevernments Lens - https://docs.aws.amazon.com/wellarchitected/latest/government-lens/government-lens.html?did=wp_card&trk=wp_card


Machine Learning Lens - https://docs.aws.amazon.com/wellarchitected/latest/machine-learning-lens/machine-learning-lens.html

SaaS Lens - https://docs.aws.amazon.com/wellarchitected/latest/saas-lens/saas-lens.html?did=wp_card&trk=wp_card

IoT Lens - https://docs.aws.amazon.com/wellarchitected/latest/iot-lens/abstract-and-introduction.html?did=wp_card&trk=wp_card

Data Analytics Lens - https://docs.aws.amazon.com/wellarchitected/latest/analytics-lens/analytics-lens.html?did=wp_card&trk=wp_card


Healthcare Industry Lens - https://docs.aws.amazon.com/wellarchitected/latest/healthcare-industry-lens/healthcare-industry-lens.html?did=wp_card&trk=wp_card


Container Build Lens - https://docs.aws.amazon.com/wellarchitected/latest/container-build-lens/container-build-lens.html?did=wp_card&trk=wp_card

Serverless Applications Lens - AWS Well-Architected Framework https://docs.aws.amazon.com/wellarchitected/latest/serverless-applications-lens/welcome.html?did=wp_card&trk=wp_card


Hybrid Networking Lens - https://docs.aws.amazon.com/wellarchitected/latest/hybrid-networking-lens/hybrid-networking-lens.html?did=wp_card&trk=wp_card


Introduction - https://docs.aws.amazon.com/wellarchitected/latest/games-industry-lens/games-industry-lens.html?did=wp_card&trk=wp_card

SAP Lens - AWS Well-Architected Framework - https://docs.aws.amazon.com/wellarchitected/latest/sap-lens/sap-lens.html?did=wp_card&trk=wp_card


Streaming Media Lens - https://docs.aws.amazon.com/wellarchitected/latest/streaming-media-lens/streaming-media-lens.html?did=wp_card&trk=wp_card


Overview - https://docs.aws.amazon.com/wellarchitected/latest/iot-lens-checklist/overview.html?did=wp_card&trk=wp_card


Financial Services Industry Lens - AWS Well-Architected Framework - https://docs.aws.amazon.com/wellarchitected/latest/financial-services-industry-lens/welcome.html?did=wp_card&trk=wp_card


High Performance Computing Lens - AWS Well-Architected Framework - https://docs.aws.amazon.com/wellarchitected/latest/high-performance-computing-lens/welcome.html?did=wp_card&trk=wp_card