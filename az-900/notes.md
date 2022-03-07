# Exam AZ-900 Prep

[Azure Fundamentals (AZ-900)](https://docs.microsoft.com/en-us/learn/certifications/azure-fundamentals/)

## Why become certified?

Other than to collect all the certs? Mostly to get a much better understanding of Microsoft Azure, to greatly benefit my
current role at WPHL. I think the AZ-900 cert is a great introduction to Micorsoft Azure, which I am not too familiar with.

[Developer Certification Path](https://docs.microsoft.com/en-us/learn/certifications/roles/developer)
[Administrator Certification Path](https://docs.microsoft.com/en-us/learn/certifications/roles/administrator)
[DevOps Certification Path](https://docs.microsoft.com/en-us/learn/certifications/devops-engineer)

## Module 1: Intoduction to Microsoft Azure Fundamentals

Big picture view of Azure

What is Azure? Microsofts cloud infrastruture (e.g. AWS, GCP)
200+ products and services

What is cloud computing? All the hardware is somewhere else, pick and choose the services you need (e.g. compute power
and storage). Shrink and grow resources as needed

benefits? don't have to maintain hardware, its "pay as you go", lowers operating costs because you are essentially
"renting" while you need. Its "always" up

Is Azure right for me? Probably, but IT said its the only I can use ;)

Most start with "can I do this on Azure?" and try this on virtual machines (VM), but as time goes on they expand into
the other services provided by Azure

Azure Marketplace - ready to use apps on Azure (e.g. debian builds)
    *In the Azure Marketplace you can find, try, buy, and deploy the software and services you need to build new solutions
    and manage your cloud infrastructure. You can provision end-to-end solutions quickly and reliably, hosted in your
    own Azure environment.*

Behind the scenes
- virtualization via hypervisor
- fabric controllers manage servers
- Orchestrator sends requests to the fabric controllers
- API and Portal interact with the orchestrator

Tour of Azure
- compute services
    - VMs, containers and microservices
    - Azure Virtual Machines, Azure Batch <-- most likely to use
    - Azure Container Instances, Azure Functions <-- seem pretty interesting
- cloud storage
    - disks on VMs, or file shares and DBs
- networking
    - private connections, firewall ports, ddos protection
- app hosting
    - run web apps on managed platform
    - azure marketplace
- AI
    - machine learning, searching data
- IoT
    - sensors and device management
    - dashboards
- integration
    - logic apps and connections between systens
- security
    - Azure identity management controls access to Azure

## Module 2: Azure Fundamental Concepts & Architectural Components

hybrid - on-premise and cloud

vertical - make instance larger

- With vertical scaling, computing capacity can be increased by adding additional RAM or CPUs to a virtual machine.

horizontal - add more instances

- With horizontal scaling, computing capacity can be increased by adding instances of a resource. 

capital expidenture

- significant upfront spending on infrastrure (overall cost falls as time goes on)
- on-going maintenance and personel
- assets, and depreciates

operational expenditure

- no upfront costs, pay as you go
- goes on taxes for this year

infrastruture as a service (IaaS)

- complete control over the hardware
- most flexible
- think VM

Platform as a Service (PaaS)

- think Terra

Software as a Service (SaaS)

- think Office 365

Serverless Computing

- no hardware managing
- tasks are being triggered by events
- seems like taking advantage of the offered products/services
    - e.g. GCPs workflows

deployment models

- public
    - offered over public internet
    - third party
- private
    - compute resources used exclusively by business
    - your own and thirdparty
- hybrid
    - combination of public and private cloud

levels

management groups - manage access policy and compliance

subscriptions - users accounts and resources subscribed to (manage costs)

resource groups - logical container of resources

resources - services

subscriptions and management groups

Azure subscriptions

- use to create cloud base resources on Azure
- authenticatd and authorized access
- logical unit of Azure AD
- two types
    - billing boundry
        - how its billed
    - access control boundy
        - access based on subscription
        - e.g. x subscription as access to XYZ
        - y subscription has access to Z
- resource access is handled at the subscription level
- organizational
    - IT has full reigh
    - I have limited
- billing
    - production vs dev subscriptions
    - allows to see charges by subscription
    - billing profiles
        - has its own payment method
- subscription limits
    - limit to 10 subscriptions per-account by default

management groups

- containers for subscriptions
- subscriptions inherit all policies placed by a management group
    - limit regions for VM creation
- organize resources into hierarchy
- examples
    - HR, IT, Marketing management groups
- important things
    - 10000 max groups
    - 6 levels of depth (not including root and subscription)
    - only one parent
    - many children
    - single hieracrhy

Resources and resources management

- resources
    - manageable item available in azure
        - VMs, apps, networks
        - any azure service
    - must be a member of a resource group, and it can only be in a single group
- resource group
    - a set of resources you want to mange as a group
    - logical container
    - provides order in azure
- ideas
    - organize by life cycle
        - if delete group, all resources die
    - apply permissions to a group
        - role base access

Azure resource manager (ARM)

- create, update, delete resources
    - google cloud console?
- many ways to access
    - powershell, APIs, SDKs, etc...
- templates
    - json file on what you want launch
- deploy
- redeploy
- define dependencies
- apply access control
- apply tags
- clarify billing

Azure regions

- datacenter in a prticular region
    - e.g.  east-us
- can host apps on multiple regions for redundancy

Availability zone

- phisically separate datacenter is region
    - if one zone goes down, the others stay up
    - high-speed fiber optic connections
- specific datacenter in a region
    - each east-us-1 vs east-us-2
- expect costs for duplicating across zones
- zonal services
    - you specify it
- zone-redundant services
    - storage
- minimum of 3 zones in a region
    - but not all regions have zones

Geographies

- region pair
    - west-us and east-us
    - if one fails it will fall back on the other
- help avoid natural distasters
    - e.g. hurrican flooding on east coast, or earth quake on west coast

Azure has the most global regions

- brings you app closer to the user

## Module 3: Azure Database, Analytics, & Compute Services

Azure Cosmos DB

- globally dist, multi model (99.999% availbility)
- scale
- fast access via apis (milli second)
- supports schema less data
    - gcp's big query?
- atom record sequence (ARS?)

Azure SQL Database

- Microsoft SQL server
- features
    - PaaS
        - managed service
    - updates, backups, etc.. handled automatically
    - 99.999% availibility
- relational, and non-relationsal (gaph, json, xml)
- newest features always available
- azure db migration service

Azure SQL Managed INstance

- PaaS
- benefits
    - no longer need to maintain hardware
    - agility (quick change, updates, backups)
    - backup retention period
- specific options
    - server level collation set at creation
        - can't change after instance created
    - Discover->Assess->Migrate->switch over

Azure Database for MySQL

- Uses MySQL
- useful for LAMP stacks
- uptime, security, data protections, backups
- service tiers
    - small to large

Azure Database for PostgreSQL

- uses PostgreSQL community version
- all the benefits as previous (availaility, backups, etc...)
- deployment options
    - single server
        - vertical scale (more ram bigger drive)
        - pricing tiers
            - basic, general, memory optimized
    - hyperscale citus
        - horizontal scale via sharding
        - query paralellization

Big data and analytics

- big data
    - large volumes of data
- Azure services
    - synapse analytics
        - query data on you terms, serverless or with servers
    - hdinsight
        - spark, hadoop, 
        - extractions o
    - data bricks
        - spark
        - python, scala, r and sql
    - data lakes analytics
        - write queries 
        - only pay for job while running

### Compute fundamentals

Azure compute services

- disks, processors, memory, etc...
- vitual machines
    - software emulations of physical computer
    - IaaS
    - total control of hardware and software
    - VM Scale Sets
        - deploy and manage group of identical VMs
        - go up or down based on demand
- contaier services and kubernetes
    - bring your own container
    - kubernetes
- app services
    - PaaS
- Azure Functions
    - work in response to an event
        - rest request, trigger, timer, etc...

When to use Azure VMs?

- total control of OS
- ability to run costom software
- custom configs
- VM Image
    - template to create VM, includdes OS and some tools
    - can custom VM images be made? similar to AWS AMI
- reasons
    - during testing and development
    - running apps in the clous
    - expanding datcenter
    - disaster recovery
- "lift and shift"
- VM scale sets
    - load balanced identical machines
    - centrally manage, config numerous VMs easily
- Azure Batch
    - large scale parallel bactch jobs
        - HPC
    - synonymous with AWS Batch
    - plan to use this for Nextflow

Azure container services

- respond to changes on demand
- docker

Kubernetes

- container orchestrator
- distrubted architecure
- managing container based workflows

Microservices

- collection of small autonomous services
    - Website example
        - container hosting front-end
        - container hosting backend
        - another hosting storage
- each microservice and be scalled independently
- if a service goes down, it shouldn't cause the whole app to fail
- Use APIs to communicate

Azure App Service

- build and host web apps, and other types of apps
- supports windows and linux
- can deploy from git repos
- app service plan
    - determines ahow much resources your app needs
    - there is a free-tier
- Web Jobs
    - run programs

Azure Functions

- event driven
    - triggered by things like, time, api, queues, etc...
    - GCP workflows?
- serverless computing
    - abstraction of servers, infrastructure, etc...
    - never explicitly researve servers
- micro billing
    - only pay for time the code ran

Azure Funcitons and Logic Apps

- Functions
    - can be pretty much any language
    - work should be complted super fast
    - not really meant for long running jobs
    - stateless and stateful
    - can be migrated to VM
- Logic Apps
    - trigger logic based on event
    - executes workflows
    - creates logic app instance
    - created via GUI on azure
        - json schema
        - 200 plus connector and processing blocks

Windows Virtual Desktop

- basically runnning windows on VMs
- cloud hosted windows
- acces from anywhere
- why?
    - best user experience
    - no need to purchase machines
        0 can easily vertical scale
    - you are screwed though if internet goes out!
    - can make personal persistent desktops
    - centralized security
        - 2fa, data access
        - reduced chance of sensitive data on personal machine
- simplified management
    - can load balance
    - can allocate users on a single machine
        - only avialable on Azure (multiple users using same machine at same time as different users)
- can save money with reservations
    - e.g. pay for 3 years up front
- can use licenses you already own to save costs
- separates the compute enviroment from the users device
    - no PHI on the user machine

## Module 4: Azure Storage & Networking Services

Azure Storage

- create azure storage account
    - same as bucket?
- Disk storage
    - Azure VMs use Azure Storage, but disks attached to VM cannot be accessed on Azure Storage
    - many different speeds
    - VM can have multiple disks attached
- Blob Storage
    - text or binary
    - unstructured, so no limits on types of data stored
    - does not require thinking about disks
    - upto 8tb of data for VMs
- Azure Files
    - mounted on the cloud or windows, linux, macos
    - samba share
    - reasons to use
        - on premises apps
        - store configs for multiple VMs
        - write data to share and process later
    - data is encrypted at rest
    - can access via url
- blob storage tiers
    - hot access
        - storaes data accesed frequently
    - cool access
        - must be sotread for 30 days
        - lower availability
    - archive
        - must be stored for 180 days
        - stores data offline, charges incurred for bringing back online

Azure Networking

- Azure virtual networks
    - multiple isolated virtual networks
    - VM can connected to internet by default
    - can connect multiple services and vms
    - can span local and azure
    - point to site virtual netowrks
        - encryted
    - site-to-site
        - linked on on prem VPN
        - Azure devices appear on local netwrok
    - Azure ExressRoute
        - doesnot travel over internet
    - Network Security Groups
        - multiple inbound/outbound rules
    - Network Virutal Applieance
        - emulates locla hardware
        - running a firewall
    - Virtual networking peering
        - link virtual networks
        - user defined routing
- Virtual network settings
    - basic to advanced settings
        - ddos protect, subnets, vnets, etcc
    - name must be unique
    - address space
        - similar to IP adressing scheme
    - subscription on applies if there are multiple subscriptions
    - subnet names have controlled characters
    - DDoS protection is a paid feature
    - additional settings
        - network security group created separate
        - linked to vnet, and routes created
        - settings can be chaged on console or cli
- Azure VPN gateway
    - connect private networks over public space
    - site-to-site
    - point-to-site
    - network-to-network
    - VPN type
        - policy-based
            - static IPs
            - support for IKEv1 only
            - static routing
            - legacy compatibility
        - route-based
            - IPSec tunnels are used
                - don't need to know all the IPs
            - more resiliant to changes
            - IKVE2 support
            - wildcard selectors
    - Gateways come in Tiers
    - only one VPN gateway in a virtual network
    - on-prem resources
        - static ipv4
    - can have redundant deployments
- Azure ExpressRoute
    - any-to-any connecitons
    - do not go over the public internet
    - Layer 2
        - data layer
    - Layer 3
        - networking layer
        - redundant connections use L3
    - "connectivity partners"
    - ExpressRoute Global Reach
        - connect multiple express route
    - co-located providers
        - data center is located in datacenter
    - point to point
        - datacenter
    - any-to-any
        - uses WAN
    - security considerations
        - private connection, no exposure to public internet
