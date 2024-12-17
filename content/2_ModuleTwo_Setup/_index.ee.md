---
title: "AWS Hosted Workshop Setup" # MODIFY THIS TITLE IF APPLICABLE
chapter: true # MAKE SURE YOU SET THIS TO FALSE IF USING SELF-GUIDED SETUP
weight: 2
---

# AWS Hosted Workshop Setup <!-- MODIFY THIS HEADING -->

![Architecture Diagram](Architecture.png)

## Prerequisites 
 <!-- MODIFY THIS SUBHEADING -->

 pg_dump + restore workflow:

# AWS Section: 

## RDS connection string 
    
    Docs for how to get an RDS connection string: https://docs.aws.amazon.com/AmazonRDS/latest/AuroraUserGuide/Concepts.DBInstance.Connection.html

    If you don't have an RDS connection string that you can use, for this co-hosted workshop, we will be pre-provisioning a workshop-specific RDS cluster/ AWS account. 
## AWS deployment region
    For the workshop, we will be using the us-east-1 region. 
    
    How are we going to generate the connection string for an RDS cluster and Amazon account? 
    Will we be able to seed the RDS cluster with data ahead of time? 
    
    If not, what is the fastest way to get data into the RDS cluster?  


# Neon section 
## A Neon account
    Link to our Quickstart Neon "Getting Started" Section: 
## Neon database (deployed to the same AWS region as your RDS database) 
- While not absolutely necessary, using the same AWS region can help reduce egress charges. Neon does not charge for ingress. 


## Gitub repository access to Actions and Secrets
- Instructions for getting started with GitHub Actions and Secrets. (Maybe record a video for this?)


If you don't have an RDS connection string that you can use, you can use the following steps to create one. In the case of this co-hosted workshop, we will be walking you through the steps to create a Neon Twin using a workshop-specific RDS cluster/account. 




## Quickstart
[View GitHub Workflow](https://github.com/neondatabase-labs/rds-to-neon-twin/blob/main/.github/workflows/create-neon-twin-default.yml)


{{% notice warning %}}
The examples and sample code provided in this workshop are intended to be consumed as instructional content. These will help you understand how various AWS services can be architected to build a solution while demonstrating best practices along the way. These examples are not intended for use in production environments.
{{% /notice %}}


#### AWS Hosted Setup <!-- MODIFY THIS SUBHEADING IF APPLICABLE -->
A brief overview of submodule two explaining setting up the workshop with the AWS EventEngine.

### Next Section Heading <!-- MODIFY THIS HEADING -->
This paragraph block can optionally be utilized to lead into the next section of the workshop.


#### Example Content Guidance
# Event Engine <!-- MODIFY THIS HEADING -->
Welcome to the Event Engine Setup section! This means that you are attending an AWS Hosted Workshop! Event Engine is a tool created at AWS that provisions AWS accounts for workshop events like this! These accounts will automatically terminate 24 hours after the workshop begins so participants don’t have to worry about leaving anything on. Each workshop participant will receive their own Event Engine AWS account.

Here is a preview of what we will be setting up:

    Creating a Cloud9 IDE Workspace
    Creating an IAM Role
    Attaching an IAM Role
    Configuring Cloud9 Workspace

The next page will show you how to gain access to your Event Engine dashboard!
