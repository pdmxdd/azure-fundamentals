# Azure Fundametals

Mahlah Murray -- Azure Technical Trainer -- mahlah.murray@microsoft.com

Would like to know if we get the cert

[shared course materials](https://docs.microsoft.com/en-us/learn/paths/azure-fundamentals/)

## Intro

This course is a high level overview of cloud computing in Azure.

- public, private, hybrid clouds
- infrastructure, platform, SaaS
- core Azure products, services, and tools

This course maps to the AZ-900 MS Azure Fundamentals exam

http://aka.ms/azfunpath -- follow along with class -- MS will not give out slides

### No Hands-On Components

This course is just conceptual

Did some menti stuff to get an understanding of the class menti.com

## Module 1 - Cloud Concepts

## lesson 1 - Why Cloud Services

- compute power
- storage
- networking
- analytics

key concepts
- high availability - having access with little or no downtime (patches, mainte)
- scalability - just the ability to horizontally scale
- elasticity - automatically or dynamically scale -- spun up when needed, spun down when not
- agility - add or remove resources quickly as needed
- fault tolerance - if something is down, or misfunctioning you still have access to the resource (if a component is broken, you can still access the resource)
- disaster recovery - region, or datacenter goes down you still have access
- global reach - regions all over the world to place your resources
- customer latency cap - place resources close to users (because of global reach)
- security - monitor resources, what is going on in my env and the ability to react quickly
- predictive cost considerations - highly variable, dependant on what resources, but they can be predicted? MS gives you the prediction? idk

### Economies of scale

Since MS, AWS, and Google have tons of money they buy all the infrastructure and then make it avaiable as a service to users, so they are passing services to you -- user's just rent space from MS, AWS, or Google. Used Costco, and Sam's club as example.

### CapEx vs. OpEx

Capital Expenditure (CapEx) - paying for physical infrastructure up front -- paying for goods instead of services

Operational expenditure (OpEx) - paying for services when you use them -- pyaing for services instead of goods

### Consumption based model

- no upfront costs
- no need to purchase and manage infra
- ablity to pay for additional when needed
- ability to stop paying for resrouces that aren't needed

## Lesson: cloud models

### public cloud

services -- owned by MS, or AWS, or Google and leased/rented by individual orgs/companies

Sharing a taxi with others as an example

- owned by cloud services, or hosting provider
- provides resource and services to multiple orgs and users
- agility
- consumption-based
- public access
- OpEx

### private cloud

goods -- owned by individual company

- owned and operated by the org that uses cloud resources
- orgs create a clould env
- capEx
- private network access
- deep tech skills required
- control
- security

### Hybrid Cloud

service?

Combines public and private clouds to allow apps to run in th emost appropriate location

I want to place apps in the specific location -- public facing website in public cloud, but the data is in the private cloud, and they are connected

## Lesson 4

### shared responsbility model

private cloud - you manage everything from storage, to data & access
IaaS - cloud host manages storage, networking, and compute
PaaS - cloud host manages storage, networking, compute, VM, OS, runtime
SaaS - cloud host manages storage, networking, compute, VM, OS, runtime, and Applications

### IaaS

- most basic cloud computing services category
- when you need to control and manage the VM, and OS
- users are responsible for purchasing, installing, configuring, an dmanaging their own softare, operating systems, middleware, and apps

### PaaS

example of startup

I don't have the capital, or employees to do those tasks

I just want to deploy my apps, and I want them deployed as quickly as possible.

- provides env for building testing, and deploying software
- users manage apps and data & access
- don't have to worry about the middleware

### SaaS

centrally hosted and managed software for end users. Users connect to and use cloud-based apps over the ineternet. For example, MS Office 365, email, and calendars

Gmail would be an example of that as well, or really any of the software in the g-suite (calendar, drive, etc) They are just software available for you over the cloud

### Cloud service comparison

- IaaS is the most flexible and offers the most user control, but has to eb configured
- PaaS is the quickest to deploye
- SaaS users pay for the software they use on subscription model

Example: Pizza as a Service

Traditional (private) - I bought the ingredients and created the pizza from scatch with my stuff
IaaS - Take and Bake - I boght a freezer pizza and cooked it
PaaS - Pizza Delivered, I just provided plates, and soda
SaaS - Dined Out - they did everything

### Lesson 4: module review q's

- With SaaS what are you responsbile for? (HA, scalability, Installation, Config) -- config (they don't mean config of infrastructure, or networking, they mean end-user configuration of the application, or configuring what users have access to the Software)
- With PaaS solutions, you have full control over the OS? (true, false) -- false
- select two public cloud chars (dedicated, limited storage, metered pricing, self-service management, unpredictable cost) -- metered pricing, self-service management
- the ability to automatically or dynamically increase resources as neede dis an exmaple of... (HA, scalabillity, elasticity, agility, fault tolerance) -- elasticity
- hybrid clould woul mean that you.. (migrate all on-presimses rsources, can extend your infra, allow public access to your on-premises resources) -- can extend your infra
- public cloud is true? -- each customer uses a portion of the resources
- who is respo to kee ypur VM running in Azure? (ms, both, me) -- both ms and yourself
- 3 benefits of using public cloud services: elasticity, agillity, economy of scale
- when using IaaS services, you are resp for which 2 components: applications, OS
- office 365, onedrive, and dy365 are examples of PaaS solutions: false

## Module 2: Core Azure services 

### Lesson 2

#### Regions

- 54 regions across the globe
  - collection of data centers

#### region pairs

- protects you from region disasters
- you can configur a fail over into another region
- automatically chosen for you if you choose East US you are automatically paired with West US
  - you have to set up both regions, you have to select to have a fail over region -- you just don't have to select the actual region, because they are defined by region pairs

#### geographies

- 2 or more regions (Americas, Europe, Asia Pacific, Middle East, Africa, etc)

#### availability options

- Single VM - 99.9% SLA
- Availability Sets - 99.95% SLA
- Availability zones - 99.99% SLA
- Region Pairs - Multi Region Disaster Recovery

#### availability sets

Keep apps online during maintenance or hardware failure. This is inside one data center.

- Update Domains (UD): scheudled maintenance, perforamcne, or security updates, are sequenced through update domains -- up to 20
- Fault domains (FD): provide a physical separation of workloads across different hardware in data center -- there are 3

#### availability sets

- physically separte locaiton within an azure region
- takes availability sets to th enext level
- incldues one or more datacenters, equipped with independent power, cooling, and networking
- acts as an isolation boundary
- if one availaiblty zone goes down, the other continues working

#### resource groups

like file manager on your computer each resource must live in a resource group (this is more like AWS VPC) every resource you spin up 
a resource can only exist in one group at a time -- but you can move it across different groups

- continaer for multipe resources that share the same life cycle
- aggregates resources into a single manageable unit
- every azure resource must exist in one and only one resource group
- secure at the resource group level using RBAC

you can configure your resource group however you want, although there are best practices -- you can put multiple types of resources in one resource group

a resource group is just a folder holding your resources

WHEN YOU DELETE A RESOURCE GROUP all the resources in that group are deleted

you can set policies, and rules for resource groups based on company needs, to aid in organizaing your resources

resources can communicate with resources in different regions

you can have resources over different regions in the same resource group

#### Azure resource Manager

(ARM)

Manages and creates resources -- so if you want to deploy a VM you can do it with an ARM template

- provides management layer for resources and resource groups
- create, configure, manage, and delete
- orgainzes resources
- control access and resources
- automate using different tools and SDK

you can create your own templates to spin up resources, or lots of copies of the same resource

#### Brief look at Azure Portal

home screen
left side panel are called blades (possible test question)

search bar, or configureable panel with blades that you can favorite

searched for resource group -- selected one, and it's a collection of multiple different types of resources

### Lesson 3

#### Azure compute services

lots of resources that are on demand

we will look at VMs and containers, but there are more

#### Virtual Machine services

- Azure VMs - IaaS to create a VM in the cloud (AWS image on EC2 is my guess)
- VM scale sets - Designed for auto scaling of identical VMs (similar to AWS autoscaling groups based on an image)
- App services - PaaS offering to build, deploy, and scale enterprise-grade web, mobile and API apps
- Functions - Performs compute actions based on an event (AWS Lambda? seems similar, but not exactly the same)

#### Back into the Portal -- demo

creating a virtual machine

searched, or clicked Virtual machine -- clicked add -- basic web form iving you options (very similar to AWS)

- subscriptions
- resource group -- can create new from this wizard
- VM name -- no best practices from MS, just something relevant, or descriptive
- Region
- Availability options -- not all regions have zones and sets, so some options may be greyed out (set UD, and FD, if sets), if zones you select how many zones
- Image (ubuntu 18.04) -- just like AWS lots of public images, and you can add your own private images
- auth type -- passowrd, or ssh keys
- inboud port rules (similar to security groups)

there are lots of additional tabs and options, storage, network, management, advanced, tags, Review and Create (super similar to AWS) -- she just took the default of everything

- tags -- just like AWS -- just a tag with some information to help identify

- auto shutdown is a cost saving feature -- it will shut down the VM for you to save cost, but there isn't an auto-startup -- there is a script on GH that you can load into the config that will do that, it's just not in the azure dashboard

---- so far this is super similar to what we do in spinning up 1 EC2 with an ubuntu image for students the first time

it does some validation for you, and then you can click create machine (you can also download this as a template for automation later) -- the template is in JSON -- looks similar to an AWS cloudformation script -- but for just one resource


opening the deployed VM -- you can see the specs of the machine just created, the public IP, the private IP, the subnet, the DNS name (which you can easily configure) -- you can reconfigure size, or CPU just like AWS -- not clear if you need to shut down the machine (probably)


#### Virtual Machine Services

----great question about adding just memory, but not CPU -- not a clear answer -- I would imagine this is possible, but it might not be a VM, more like a function would be my guess to answer this guys question----

#### container services

contianers are a virutalization env. However, unlike VM you do not manage an OS. Containers are meant to be lightweight, and are dsigned to be created, scaled out, and stypped dynamically.

- Azure Container instances - PaaS offering that allows you to upload your containres, which it then will run for you
- AKS (Azure Kebernetes Service) - A contianer orchestartor service for managing large numbers of containers

----idea API as container, ES as container, geoserver as container, upload to AKS -- and put frontend just connecting to the API container ----

#### azure network services

- Azure Virtual Network - provides secure comm between azure resources (similar to VPC?)
- scoped to a single region; however, mutiple virtual networks from different regions can be connected using virutal network peering (very similar to VPC)
- Azure Load balancer - auto scales to create ha access to applications or resrucs
- use load balancer with incoming traffic, port forard to specific traffic, to VMs in your virtual network (exactly how the load balancers work in AWS, from a high level)

#### Azure network services

- VPN Gateway
- send encrypte dtrafffic between AVN, and on premises locaiton over the public internet
- secure connection form on-premises to azure over the internet

- Azure Applicaiton Gateway
- web traffic load balancer that enables you to manage traffic to your web apps
- connection through which users connect to your application 

- allows users access to the application, whereas the load balancer does not discriminate end-users or servers (that's what I got out of the answer)

- content delivery network - provides a distributed network of servers that efficiently delvier web content, in their local region
- provides content to users in their local rgion to minimize latency

CDN allows you place your services closer to users -- this is all about regions as well

#### Azure data categories

- structure data - adheres to schema, storable in reltaional, like sensor data nd finacial dat
- semi-structured data - ad hoc schema with less organzied fields and properties, non retalional, or NoSQL, books, blogs, HTML docs
- unstructred data - has no schema, non-relational or blob data, images, JSON objects

#### Azure sotrage services

- Blob storage - junk drawer, no restrictions on the kinds of data it can hold, highly scalable (block type storage, not file type storage)
- disk storage - provides dikss for VMs, apps, and other services
- file storage - fully managed file shares in the cloud -- immediate access
- archive storage - storage facility for data that is rarely accessed -- 180 days after storage it is available for access

#### DEMO creating blob storage

- went to storage account -- add -- looks very similar to the VM creation wizard -- name, locatoin, resource group, etc. All sorts of additional options that can be configured, I assume she will select all defaults. -- storage account name is GLOBAL UNIQUE

- account kind is the type of storage
- replication - for your sotrage account, LRS (local redundat storage (3 times replication in 1 data center)), GRS (3 zones across the selected region), RA-GRS (read access across all 3 zones)
- performance - standard (HDD) or premium (SSD) most options have options

Storage Account can contain multiple types of storage -- blob, file, archival etc


MS doesn't show you the estimated prices until the end -- uniles AWS which shows you many of the price estimations at selection time

access tier -- cool, or hot (hot means we will be accessing it frequently), cool is the opposite (hot cost less to access, but more to store)

ACCESS TIER is how you make something archival -- so blob, or file can either be hot or cool

archive is both writing, and reading -- so you can stream to it, bu tnot read out of it

cool is good for putting data in, but not accessing in 180, hot is for putting data in, or accessing data that you need or use frequently

according to the shared resources -- maybe cool doesn't mean archival -- there is some language about cool being 30 days, and archive is 180 days


took all the defaults and then reviewed and created -- same thing some validation,a nd then click create and it spins up the storage account



you then click the storage account, and from here you can add more containers, tables, containres, file shares, queues

she clicked containers to add a container to this storage account -- she gave it a name -- it's not global unique, if she wants to provide access to this container, she can select if it's public, or private

selects ok, then she uploads an image to it -- so this is just blob storage you can put whatever you want in, and it can scale almost infinitely -- option to override file if it already exists

she uploaded some image, and it put it in the container named "images" at the storage container account

you can click Generate SAS which will generate a URL so users can gain access to the data -- so you can make it a private Data Storage Account, and you can still grant access to users on a per use basis




#. Create Account Storage
#. Create Container in Account Storage


#### Azure Database Services

we will talk baout 3, but there are more

- Azure Cosmos DB - PaaS, globally distributed database service that enables you to elastically and independently scale throughput and storage
- Azure SQL Database - RDBMS (DaaS) based on the latest stable version fot he Microsfot SQL Server datbase engine
- Azure Database Migration - fully managed service designed to enalbe seamless migrations from multiple database sources to Azure data platforms with minimal downtime.


#### Demo adding a Azure SQL DB

search of select SQL database -- PaaS

click add -- same looking wizard, resrouce group, db  ane, what server, other options, and then review and create -- validates and then create -- wait for it to be deployed

clicked the DB resource to show us specs, but we didn't do anything with it, we didn't try to connect to it, we didn't put it on a network, it's just there


#### Azure Marketplace

- marketplace with MS things, and independant software dvendors, and starts ups that offere solutions and services for azure
- azure customers, it professionals and cloud devs can find, try, purchase and provision azure applicaitons and services from certified providiers
- close to 10000 product listings

#### Azure marketplace demo

- lots of services to select from


#### break for lunch

- called patrick
- ate lunch
- talked to Ryan and Maryam about LC stuff


#### talked about Azure Solution Architect Learning path

there are a bunch of certs, and exams, and 4-5 day classes with hands on labs

### Lesson 4: Azure solutions

#### IoT

- Azure IoT Central - fully managed global IoT SaaS solution
- Azure IoT Hub - managed service hosted in the cloud that acts as a central message hub for bidirectional comm between IoT application and devices
- There are more

#### Big data and Analytics

- Azure SQL Data Warehouse - enterpirse data warehouse that leverages massively parallel processing to run complex queries quckikly across petabytes of data -- parallel processing
- Azure HDInsight - open-source analytics service for enterprises. it is a cloud service that makes it easier, faster, and more cost-effecitve to process massive amounts of data 
- Azure Data Lake Analytics - simplifies big data. insetead of deploying and tuning hardware you write queries to transform your data and extract valuable insights

#### AI

- Azure Machine Learning service - provies a cloudbased env used to develop, train, test, deploy, manage, and track machine learning models
- Azure Machine Learning Studio - collaborative, grad and drop visual workspace wher eyou can build test, deploy machine learning solutions without needing to write code

#### Serverless computing

- Azure Functions - code running your service and not the underlying platfom or infra. Creates infra based on an event
- Azure Logic Aps - cloud service that helps you automate and orcestrate tasks, business processes, and workflows when you need to integrate apps, data, systems, and services -- these seem powerful for mood analytics, happines results
- Azure Event Grid - intelligent event routing service that uses a publish-subscribe model for uniform event consumption

#### DevOps

- Azure DevOps services - provides development collaboration tools including pipelines, git repos, kanban boards, and extensive automated and cloud-based load testing
- Azure DevTest Labs - Allows you to quickly create environments in Azure while minimizing waste and controlling cost

this is separate from the portal we looked at today

azure.devops.com or something or devops.azure.com or something

#### Azure App Service

quickly and easily build web & mobile apps for any platform or device
- multiple langauges and frameworks
- DevOps optimization
- HA, global scale
- connectoins to SaaS platforms and on-premise data
- security
- app templates
- serverless code

### Lesson 05: management tools


#### Management Tools

- Azure portal
- Azure powershell and azure command-line interface (CLI) -- you can use BASH!!!!
- Azure Cloud Shell
- Azure mobile app
- Azure ReST API

#### Demo of management tools

- cloudshell the browser based terminal
- cloudshell icon in the top right hand bar (looks like a terminal icon)

it brings up a window and a popup came out about no storage mounted, she created some storage -- it won't prompt for attaching storage

now she is in a terminal -- it defaults to powershell, but there's a dropdown that you can change to bash

this is just a terminal for your global azure account, it's not attached to any resource you have created

but it can be used to programmatically create resources, and manage them

to do it from your own machine you will have to access the REST API would be my guess -- some form of tool that hits that REST API

azcli -- this would probably be very similar to the AWSCLI

#### Azure Advisor

recommendation tool in your azure subscription

- analyzes deployed azure resources and recommends ways to imrpove availability, seufiryt performance, and costs
- get proactive, actionable, and personalized best pracitce recommendations
- improve the performance, security, and availability of your resources
- id opportuintes to reduce your azure costs

#### module review questions

- what terms from the below list are valid core arch components of MS azure (region, AZ, resource grou, availability set)
- first thing you will create in azure subscription is (resource group)
- every resource in azure must exist in one and only one what (resource group)
- azure advisor recommends on VM network interface card settings (false)
- to make sure VM hosted ervices are available should a single data center fail you should choose 2 (different availability zones, and different regions)
- if you delte a resource group all resources will be deleted (true)
- resource groups can containe resources from different regions (true)
- which Azure management tool(s) can be used to manage a linux VM in Azure? (azure portal, azure cli, azure powershell)
- When you deallocate a VM in azure you will continue paying for (storage)
- to connect your on-premises network to an azure virtual network use (vpn gateway)
- storage account autoatically maintains backups of your data (false)
- which service provides a globally distrinuted database capable of stroing json files (cosmos db)
- to deploy 10 identical VMs simultaneously (arm template)

## Module 03: secuirty privacy, compliance, and trust

### Lesson 2 securing network connectivity

#### defense in depth

- layered approach to securing computer systems
- provides multiple levels of protection
- attacks against one layer are isolagted from subsequent layers

top to bottom (physical security data center's are inacessible, identity & access, perimeter, network, compute, application, data)

- physical security - data center's are inacessibile buildings
- id and access - 

she didn't explain the rest of the tiers

#### shared security

- migrating from a customer controlled to cloud based data centers shifts the resp for security
- security becomes a shared concern between cloud providers and customers

Iaas - physical hosts, phsyical network, phsyical datacenter
PaaS - + OS
SaaS - + more things

#### Azure Firewall

stateful managed, firewall as a service that grants/endies server access absed on originating IP address, to prtoect network resources.

security group?

- applies inbound an outbound traffic filtering rueles
- build in HA
- unrestricted cloud scalability
- uses azure monitor logging

you can monitor your Azure firewalls -- I don't know how to monitor a Security Group (AWS)

#### Azure Distributed Denial of Service (DDoS) protection

DDoS attacks overwhelm and exhaust network resources, making apps slow or unresponsive

- sanitizes unwanted network traffic, before it impacts service availaibilty
- basic service tier is automatically enabled in azure
- standard service tier adds mitigation capabilities, tuned to prtect azure virtual network resources

#### Network Security Groups (NSGs)

Filters network traffic to, and from, Azure resources on Azure Virtual Networks (THIS IS LIKE AWS SG Azure Firewall is more like a VPC SG)

- set inbound and outbound rules to filter by source and destination IP address, port, and protocol
- add dmultipe rules, as needed, within subscription limits
- azure applies default, baseline, security rules to new NSGs
- override default rules with new, higher priority, rules

#### choosing zuree network security solutions

azure support combnined network security solutions. For example, NSGs with Azure Firewall; Web Applicaiton Firewall (WAF) with Azure Firewall.

- perimeter layer protects your networks' boundaries with Azure DDoS protection and Azure Firewall
- networking layer only permits traffic to pass between networked rsources with network secirtuy gorups inbound and outbound rules

so how they handle network layer security is a little different than AWS, it's just as configurable it just lives in a couple of different places -- this seems more granaular, whereas AWS has them in two places when you are creating your VPC and it's various rules and open subnets vs private subnets, and then also Security Groups which are similar to NSGs

#### section on auth (entication vs thorization)

didn't take notes because it's not MS specific

#### Azure Active Directory (AD)

Microsoft Azure's cloud based identiy and access management service.

similar to AWS IAM

- Authentication (employees sign-in to access resources).
- single sign-on (SSO)
- Applciation Management
- Busienss to Business (B2B)
- Business to Customer (B2C) identity services
- Device Management

#### AD demo

Azure AD Connect -- search for it

it shows you all the users, you can add users, delete users, reset their password, view logs, setup MFA -- very similar to what we see with IAM roles

#### Azure MFA

- you know
- you possess
- you are

#### Azure Security Center

monitoring service that provides threat protection across all your Azure, and on-premises, services

- provides security recommendations based on your configureations, resrouces, and networks
- monitors security settings across your on-premises and cloud workloads
- automatically applies your security policies to any new services you provision

#### Azure security center demo

just showing us what that page looks like
lots of metrics, overview of what they do, security score, resource security hygiene (telling you want isn't secure vs wha tis secure)

there are recommendations as well you click it and it shows you exactly what you need to do -- an example: advanced security details can be added to this Azure DB -- 

#### Azure Key Vault

- stores application secrets in a centralized cloud location, to securely control access permissions, and access logging.
- secrets management
- key management
- certificate managment
- storing secrest backe dby hardware security modules (HSMs)

you can control access to this key vault

secrets -- is this an appropriate place for less sensitive environment variables? -- is this accessible to running applications, and if so how?

#### Azure Key Vault demo

searched for key vault

and then added a key vault

went through the form using mainly defaults

review and create

then you she created a secret, using a webform, just typical key value pair

there is also a generate option, and it will allow you to name it and then you can say key type, RSA key size, activation date, and expiration dates, if it's enabled

so you can generate new keys, manage them from here, access them here, and share them with other resources if they need them

#### Azure Information Protection (AIP)

classifies and protects documents, and emails, by applying labels.

- automatically using rules and conditions defined by administrators
- maunally by users
- by combinbing automatic and manual methods, guided by recommendations

#### Azure Advanced Threat Protection (Azure ATP)

cloud based secruity solution for identifying, detecting, ad investingating advanced threats, compormised identities, and malicious insider actions.

- portal - dedicated portal for monitoring and responding to suspicious activity
- sensors - instealled directly onto your domain controllers
- cloud service - runs on azure infrastructure

#### Azure Policy

stay compliant with yoru corporate standards and service level agreements (SLAs) by using policy definitions to enforce rules and effects for your Azure resources.

- Evalutes and identifies Azure resources that do not comply with your policies.
- Provides built-in policy and initiative definitions, under categories sucha as Storage, Networking, Compute, Security Center, and Monitoring

allows you to control what happens in your GLOBAL azure environment -- you can give certain roles these policies, to give access to specific resource types, or regions, or availability zones, etc

very similar to IAM policies

#### Implementing an Azure policy

create policty definition - assign the definiton to resources - review the evaluation resources

#### Policy Initiatives

initiative defintions - group of policies into a single unit to track compliance at a higher scope

initiative assingments - are assigned to a specific scope and reduce the need to make an initiative definition for each scope

#### Policy demo

searched policy

#### RBAC Role based access control

- fine grained access management
- segreate duties within your team and grant only the amount of access to users that they need to perform their jobs
- enables allowing or disallowing access to the azure portal and controlling access to resources

#### Resource locks

- prtocet your azure resources from accidental deletion or modification
- manage locsk at subscription, resource group, or individual resouce level within azure portal

you can apply a lock on resources so they can't be deleted, or edited, you cannot read

#### Resource lock demo

- went to an existing resource
- selected locks from the side panel
- selected add & filled out the form
- then tried to delete it and a message came up

locks are inherited so if you lock a resource group every resource in the group inherits that lock

#### Azure Blueprints

create reusable env defintions tha tcan recreate your azure resourcew and apply your policies instantly

use azure blueprints to:
- help audit and trace your deployments, and maintain compliance using bulit-in tools and artifacts
- associate blueprints with specific Azure DevOps bulid artifacts, and release pipelines, for rigorous tracking

#### Tags

not inherited like locks

- provides metadata for your azure resources
- logically organizes resources into a taxonomy
- consists of a name-value pair
- very useful for rolling up billing information

appear to be identical to AWS tags

#### Azure Monitor

collect analyze and act on telemetry from cloud and on-premises envs to maximize your apps availabilty and performance

- starts collecting data as soon as you create an azure subscription and add resources
- activity logs record all resource creation and modification events
- metrics measure resource performance and consumption
- add an azure monitor agent to collect operational data for a resource

#### Azure Service Health

evalute the impact of azure service issues with personalized guidance and support notificaitons and issue resolution updates.

3 components:

- Azure status - global overview
- services health: customizable dashoboard for tracking the state of services in the regions you use
- azure resource health - diagnose and obtain support for azure service issues affecting your resources

### Lesson 7: compliance, trust, data protection 

#### Privacy & Compliance

- privacy statement - personal data, interactions with data, data transparency
- trust center - one stop shop for security privacy and compliance documents
- compliance terms - GDPR, HIPPA, etc
- compliance manager - assess your compliance
- service trust portal - 

#### Azure Govermnet services

meets the security and compliance needs of US federal agencies, state and local governments, and their solution providers.

Azure Goverment:
- separate instance of Azure
- physically isolated from non-US government deployments
- accessible only to screened, authorized personnel.

exmaples of compliant standards: FedRAM, NISt 8000.171 (DIB), ITAR, IRS 1075, DoD L2, L4 & L5, and CJIS

gov has their own data centers in 4 different locations

#### Azure China 21Vianet

China's first foreign public cloud service provider, in compliance with government regulations

Azure China 21Vianet features:
- physically separated instance of Szure cloud services, located in China
- operated by 21Vianet

#### lesson 8 module review

- you can download audit reports form the service trust portal (true)
- which of the following services provides status info about health of azure services (azure service health)
- which service should you use for centralized monitoring (azure monitor)
- which descriptoins from the following list describes a feature of characterstic of azure firewall (stateful firewall services built in HA; fully integrated with logging and analytics, a third that I can't see)
- YOu want to filger inbound and outbound network traffic to and from your Azure reousrce in your azure virtual network which service should you use? (NSG) 
- can you deallocate a VM with a read lock? (no)
- you can use a DDoS plan to allow HTTPS traffic to a VM? (false)
- to prevent credentials from being stored in web app config files use: (azure key vault)
- where can you obtain info about how MS process personal data? (MS privacy statement)
- you want to prevent users from creating resources in certain regions (use azure policy)

## Module 4 Pricing and support

### lesson 1

#### Azure subscriptions

azure account can have 1 or more subscriptions

- an azure sub provides you with authetnicate dand authorized access to azure accounts
- subs can provide billing and access control boundaries
- azure has multiple subscription offerings including free, pay as you go, enterprise agreement, and student
- an account can have one subscription or multiple subscriptions

#### Subscription offers

- free
- pay as you go
- enterprise agreement
- student
- an account can have one subscription or multipe subscriptions

#### Azure Free account

- provides 12 montsh of our most popular servicesa and $200

#### Purchasing azure products and services

three main customer types:

- enterprise - org or company that has a contract with MS to say we are going to spend X money on Azure services
- web direct - sign up through the website and get the standard pricing
- cloud solution provdiers - MS partner companies that a customer hires to build solutions on top of Azure. Payment and billing for Azure usage occurs thorugh the custoemrs' CSP

#### Factors affecting cost

three main factors:

- resource Type - anyting you create in azure, each resource costs a differnet price
- services - customer type what type of customer you are
- location - the azure infra is globally distributed and usage costs might vary between locations that offer Azure prodducts, services, and resources

#### Pricing Calc

- helps you estimate the coust you need
- azure provides a detailed estimate

#### Billing options

- pay as you go
- 1 year reserved (discount)
- 3 year reserved (bigger discount)

#### Total cost of ownership calc

I want to migrate to Azure what will the cost be

- a tool to estimate cost savings you can realize by migrating to azure
- a report compares the costs of on-premisses infrastrucrres with the costs of using azure products and services in the cloud

#### Minimizing costs

you can set spending limits

#### Azure cost management

- reporting
- data enrichment
- budgets
- alerting
- recommendation

#### Support plan options

- every azure sub includes free access to biling and subscription, support, azure products, and services documentation, online self-help documentation, white papers, and commuinty support forums

4 paid support plan options

- devleoper
- standard
- professional direct
- premier

#### Knowledge Center

serachable database that contains support q's and a's froma community of azure experts, develpoers, customers, and uesrs

#### SLAs

- SLAs document the specific temrs that deinfe zaure performance standards
- SLAs define MS commitment to an azure service or product
- Individual SLAs are available for each Azure product and service
- SLAs also define what happens if a service or prodcut fails to meet the designated availabiltiy commitments

MS gives you a credit back for the whole month if they break their SLA -- DB down for more than 4.32 minutes at 99.99% coverage

#### Composite SLAs

app service SLA is 99.95 and DB SLA is 99.99 the composite is .9995 * .9999

composite SLA will always be lower than the lowest SLA of your collection

#### accessing preview features

- preview new functionality and features for an existing service
- preview new services

#### general availability

- new features are evaulated and tested
- feature bugs go through a lifecycle of new, active, resolved, and fixed
- general availability provides succesfully tested features to all azure customers
- azure blog annoucemts is a good example

#### monitoring serviec and feature updates

- provies info about stuff coming about around Azure

#### Module review questions

- all azure services have at least a 99.9% uptime SLA (only true for paid azure services)
- which of the following defines an azure subscription (azure subscriptions are a logical unit of azure services linked to an azure account)
- which of thefollowing are used to determine azure costs fo reach billing period (usage meters)
- which componentw directly affect your VM costs in the azure pricing calucluartor (region, OS, reserved instance option)
- available purchasing and billing options for azure products and servies depend on what (customer type)
- complete the follwing sentence. Peformance targest defines within a SLA... (are specific to each azure product and service)
- a featue released to all azure coustomrees is said to have which of the following (general availability) 



##### shared resources

https://aka.ms/azfunpath
https://docs.microsoft.com
https://www.microsoft.com/learning

mahlah.murray@microsoft.com

 
