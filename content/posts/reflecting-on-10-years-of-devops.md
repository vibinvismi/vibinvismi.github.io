---
title: "Reflecting on 10 Years of DevOps"
date: 2019-12-03T16:31:17+01:00
---
> "It’s not my machines, it’s your code!" vs. "It’s not my code, it’s your machines!"

It has been 10 years since [John Allspaw](https://www.slideshare.net/jallspaw/10-deploys-per-day-dev-and-ops-cooperation-at-flickr) and Paul Hammond proposed Dev and Ops co-operation during their talk at the [2009 Velocity Conference](https://conferences.oreilly.com/velocity/velocity2009/public/schedule/speaker/24342). DevOps practise has progressed a long way since then. However, DevOps is just entering mainstream slowly now a days. DevOps practise came into existence as a way to solve never ending fights between Development team and Operations team to enable faster deployments to production. At this point, it might be a good idea to understand what exactly is DevOps? Is it a job role? Is it just about tools? Is it about some way of working or culture?

## What is DevOps

Definition of DevOps means a lot of different things to different people because it covers a lot of ground. In a nutshell, it is co-operation between developers and operations team. One popular definition of DevOps is as below:

> DevOps is the practice of operations and development engineers participating together in the entire service lifecycle, from design through the development process to production support.

People define DevOps such as "Developer - Operations collaboration" or "treating your Infrastructure as Code" or "using automation" or using a "Kanban approach" or using some "tool chains"  or even "culture". The best way to define DevOps is to consider it as an extension of Agile Development. It distills down to better collaboration of customers, product management, developers, and QA to fill in the gaps and rapidly iterate towards a better product. There are Three primary practise areas in the context of DevOps:

### Infrastructure Automation

Create your servers, OS, Configurations and Application Deployments as code.

### Continuous Delivery

Build, Test and Deploy your applications in a fast and automated way.

### Site Reliability Engineering (SRE)

Responsible for the availability, latency, performance, efficiency, change management, monitoring, emergency response, and capacity planning of services.

## Stop Hiring DevOps Engineers

One of the interesting talks in DevOpsDays Berlin by Stevan Cvetković was titled **"Stop Hiring DevOps Engineers"**. DevOps is not a role, automation or a tool. It is a way of working. This is exactly why it is so hard to implement it right. It is a set of principles that define how entire organization should be operating. 

The author of this talk recommends to imbibe DevOps culture in the entire organization. Start from the top to bottom. Ensure 100% buy-in from the top management for DevOps transformation. Identify leaders to spearhead this transformation. 

Ensure Agile is working perfectly. Agile is the strong foundation absolutely necessary for the successful implementation of DevOps transformation. Embrace experimentation and convert each failures into a learning opportunity. Make development teams care about builds and deployments. Dev and Ops teams working together can efficiently optimize delivery pipelines. 

Build shared responsibilities: ensure development team understand the impact of code changes to the customers as well as the underlying infrastructure. Invest in automation tools for Continuous Delivery and Infrastructure as Code. 

Make work visible and embrace transparency. Ensure Ops teams are aware of Product roadmap and major changes. 

Measure everything: monitor all stages of build and deployment pipeline and create visible dashboards shared with all stakeholders.  

Roll up your sleeves and encourage every engineers of development and operations teams to be DevOps Engineers.

## DevOps vs SRE

SRE is the specific implementation of DevOps at Google, while Google likes to define DevOps as a "generalization of several core SRE principles to a wider range of organizations, management structures, and personnel". SRE is a more formal implementation of DevOps practises with stringent controls. Google have lots of experience running several customer facing systems at a very large scale. Google have shared lots of details about [SRE](https://landing.google.com/sre/) and how their SRE teams works to automate, run and maintain their web-scale systems. 

