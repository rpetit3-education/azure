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

## Module 4: Azure Storage & Networking Services
