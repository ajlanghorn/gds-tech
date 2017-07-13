---
title: Hosting
layout: recommendation
expires: 2017-11-01
---

GDS follows the [Government Cloud First policy](https://www.gov.uk/guidance/government-cloud-first-policy) meaning that we prefer the use of Platform as a service (PaaS) and Infrastructure as a Service (IaaS) solutions over managing our own hardware.

## User Needs
Your hosting solution will need to accommodate the user needs of:
* service users who want systems that are highly scalable and available
* GDS administrators who want to manage their environments easily, simply and with confidence using automated tools

## Principles

GDS will build new tools on a primary cloud platform for each of PaaS and IaaS.

* we prefer systems built on a PaaS to systems built on IaaS where possible
* we prefer cloud suppliers that are well supported by common tooling to reduce cost of migrating to a new supplier

## Tools

GDS has selected two cloud platforms:

### PaaS

GOV.UK Platform as a Service (PaaS) manages the deployment of your apps and services.
* GOV.UK PaaS
  https://cloud.service.gov.uk

### IaaS

Amazon Web Services (AWS) offer scalable computing, storage and deployment services.
* Amazon Web Services
  https://aws.amazon.com

### Consider switching costs

AWS has a large number of different services available.  Some are common to many providers, such as compute and file storage.  Others are more specific to AWS itself.

#### Common services

It's fine to use the core features of AWS that are common with the biggest competitors, for example:

  * Compute (EC2)
  * Networking (load balancing and network segregation)
  * File storage (EBS and S3)
  * Hosted databases (Amazon Relational Database Service (RDS))

#### Less common services

When using less common services, such as CloudFront, Simple Queue Service (SQS), or Lambda, it may make it more expensive to switch to another provider if that is required in future.

For example, a web API service which is built entirely from Amazon API Gateway, Lambda, SNS, SES and similar services would be harder to migrate to another platform than an API built as a traditional web application and deployed to EC2.

On the other hand, a Lambda function which is used for shipping CloudTrail logs to a log provider is probably an acceptable use of a proprietary service.  It would not make sense to rewrite this Lambda function to run on EC2 hardware instead; this would do nothing to reduce switching costs.

If you are using services which are more Amazon-specific, take some time to think about what they will mean for your service.

Services which have the /potential/ to raise switching costs include:

  * API Gateway
  * AWS Directory Service for Microsoft Active Directory
  * CloudFront
  * DynamoDB
  * Lambda
  * Route 53
  * Simple Notification Service (SNS)
  * Simple Queue Service (SQS)
