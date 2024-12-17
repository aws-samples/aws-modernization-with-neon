---
title: "Introduction"
chapter: true
weight: 1
---

# Introduction

## Learning Objectives <!-- MODIFY THIS SUBHEADING -->

- Identify challenges with AWS RDS in development workflows, such as slow provisioning, collaboration difficulties, and data synchronization issues.

- Learn about Neon's capabilities like database branching, instant environment provisioning, CI/CD integration, and autoscaling to enhance development and testing workflows.
- Configure Neon as a dev-friendly alternative to RDS, enabling efficient workflows without disrupting production databases.
- Automate Data Transfer between RDS and Neon (Use tools like ```pg_dump``` and ```GitHub Actions``` to synchronize data from RDS --> Neon effectively) 
- Leverage Neon's branching feature to create isolated environments for parallel development without extra storage costs.
- Utilize features like Neon's scale-to-zero functionality to reduce costs while improving team collaboration and iteration speed.

## Does this workshop cost anything? 

Neon is currently free to use. There are different pricing plans for different use cases. However, for this workshop we will be using the free plan. If for any reason you need to upgrade your plan, you can do so by clicking on the "Upgrade" button in the top right corner of the Neon dashboard. We can also provide you with a coupon code if you think you will need to upgrade your plan. 


## Workshop Structure <!-- MODIFY THIS SUBHEADING -->

<ul>
    <li> Prerequisites *(~20 minutes)* </li>
    <li> Module 1: Addressing RDS Development Challenges and Unlocking Neon's Potential *(30 minutes)*
        <ul>
            <li> Part 1: Understanding RDS Development Pain Points</li>
            <li> Part 2:  Enhancing Development Workflows with Neon</li>
            <li> Part 3: Setting Up Your First Neon Project</li>
        </ul>
    </li>
    <li> Module 2: Set Up Environment for Neon Twin Deploy Workflow (~30 minutes)</li>
        <ul>
            <li> Path A: For Users Already Running RDS in Production or Staging </li>
            <li> Path B: For Users who are not running RDS in Production or Staging</li>
        </ul>
    <li> Neon Twin Deploy Workflow *(~30 minutes)*</li>
        <ul>
            <li> Learn how to create a "Neon Twin," a synchronized copy of your RDS database. </li>
            <li> Automate nightly synchronization using pg_dump, pg_restore, and GitHub Actions. </li>
            <li> Set up GitHub workflows to keep development environments up-to-date. </li>
        </ul>
</ul>

{{% notice info %}}
<p style='text-align: left;'>
**REMOVE:** With the exception of _index.md, the module folders and filenames should be changed to better reflect their content, i.e. 1_Planning as the folder and 11_HowToBegin as the first submodule. Changing the "weight" value of the header is ultimately what reflects the order the modules are presented.
</p>
{{% /notice %}}
