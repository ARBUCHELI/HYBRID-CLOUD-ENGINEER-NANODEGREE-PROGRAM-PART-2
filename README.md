# NUTANIX

This repository includes the theoretical courses of the Udacity's Hybrid Cloud Engineer Nanodegree Program and the solution of the quizzes and projects.  This material was created with the purpose of self reference.

# HYBRID-CLOUD-ENGINEER-NANODEGREE-PROGRAM

## Advanced Calm Features

In the following sections, we will explore several advanced Calm features, now that you’re familiar with what Calm does and how it works. We will discuss:

* Windows analogs to Linux, Cloud-init, and Shell
>> * So far, we’ve used Linux as our base for VMs and blueprints. But depending on the needs of your application or perhaps due to business directives, you may need to use Windows instead. Then, it becomes necessary to find and use alternatives to some associated components that we’ve previously discussed.

* Protecting AHV VM Workloads with Microsegmentation and Flow
>> * Nutanix Flow simplifies network and policy management with a focus towards applications, enabling applications and environments to be governed independent of the physical infrastructure.
>> * In this section, we’ll look at how it can be used to protect workloads. Later in this course, we’ll examine Flow’s security capabilities in more detail.

* Nutanix Calm DSL
>> * A domain-specific language (DSL) is a computer language specialized to a particular application domain. You can think of a DSL as a way of simplifying programming tasks that are specific to a domain or product.
>> * In this case, the Nutanix Calm DSL has been specifically written to work with the Nutanix Calm product.

* Runbooks
>> * A Runbook is a collection of orchestration tasks defining “What to do” and “Where to do it.” Calm Runbooks helps orchestrate automation tasks across infrastructure and applications in a hybrid cloud infrastructure.

* Working with Prism Central APIs
>> * Nutanix REST APIs allow you to create scripts that run system administration commands against the Nutanix cluster.
>> * The REST API exposes every capability and data point of the Prism UI and allows for orchestration and automation within the Nutanix framework.

## Working with Windows: Analogs to Linux, Cloud-init, Shell

So far, we’ve discussed using Linux as the foundation for your VM and blueprint creation, because it’s easily the most common OS for these sorts of activities. However, based on your application or perhaps due to business directives, you may find yourself needing to use Windows instead. In that case, it’s necessary to find and use alternatives to some of the associated components that we’ve previously discussed.

### Cloud-init and Cloudbase-init
If you think back to earlier lessons in the previous course, one topic that we covered was Cloud-init. Cloud-init is the reason that, when you start a cloud instance, it comes up with the required software installed, completely ready to use. It is essentially a service that’s installed inside an instance, runs on Linux workloads, and executes a series of scripts to ensure that the system is initialized as needed.

![](https://video.udacity-data.com/topher/2020/September/5f63eec9_linux-systems-updated-1/linux-systems-updated-1.png)

If the same activities need to be performed on a Windows system, the alternative is Cloudbase-init.

When deployed as a service on Windows, Cloudbase-init handles all guest initialization actions, including disk volume expansion, user creation, password generation, custom PowerShell, CMD and Bash scripts execution, Heat templates, PowerShell remoting setup and so on.

### Sysprep
Sysprep is a utility that prepares a Windows installation for duplication (imaging) across multiple systems. Sysprep is most often used to generalize a Windows installation.

During generalization, Sysprep removes system-specific information and settings such as the security identifier (SID) and leaves installed applications untouched.

You can capture an image of the generalized installation and use the image with an answer file to customize the installation of Windows on other systems. The answer file contains the information that Sysprep needs to complete an unattended installation.

### Shell and PowerShell
For scripting needs on Linux, one of the more commonly used tools is Shell. A shell, simply put, is a command-line interpreter. A Shell script is a program designed to be run by the Unix or Linux shell. Shell scripts are typically used to perform operations such as file manipulation and program execution.

The Windows alternative to Linux Shell scripting is PowerShell. PowerShell is a cross-platform task automation and configuration management framework. It consists of a command-line shell and scripting language. PowerShell is built on top of the .NET Common Language Runtime (CLR). So, while most common shells accept and return text, PowerShell accepts and returns .NET objects.

## Quiz: Analogs to Linux, Cloud-init, Shell

![](https://raw.githubusercontent.com/ARBUCHELI/HYBRID-CLOUD-ENGINEER-NANODEGREE-PROGRAM-/main/images/479.jpg)

## Protecting AHV VM Workloads with Microsegmentation and Flow

In many ways, the modern data center has outgrown the traditional perimeter firewall, thus increasing the risk of a security breach. Security controls must evolve to work within today’s IT environment — an environment that’s characterized by rapid growth, change, and complexity. Organizations need security controls that provide granular protection behind traditional perimeter security to prevent the spread of threats and protect IT assets wherever they go.

![](https://video.udacity-data.com/topher/2020/September/5f63ef03_protecting-ahv-vm-workloads-with-microsegmentation-and-flow-policies/protecting-ahv-vm-workloads-with-microsegmentation-and-flow-policies.png)

App-centric security from Nutanix Flow is the answer. Nutanix Flow simplifies network and policy management with a focus towards applications, enabling applications and environments to be governed independent of the physical infrastructure. Fully integrated into the Nutanix platform, Flow delivers powerful networking and microsegmentation functionality with an intuitive policy creation and management interface that allows IT teams to easily visualize and secure the most complex enterprise applications.

App-centric security from Nutanix Flow is the answer. Nutanix Flow simplifies network and policy management with a focus towards applications, enabling applications and environments to be governed independent of the physical infrastructure. Fully integrated into the Nutanix platform, Flow delivers powerful networking and microsegmentation functionality with an intuitive policy creation and management interface that allows IT teams to easily visualize and secure the most complex enterprise applications.

### Why Switch to App-centric, Microsegmentation-based Security
By its nature, a virtualization platform understands all of the VMs and how they are connected to the network regardless of any deployment or configurations changes. When you leverage that network knowledge, security policy becomes something that can be automated, and switching to defining security in terms of the application instead of the network endpoints just makes sense. That’s where microsegmentation and app-centric policy come into play.

![](https://video.udacity-data.com/topher/2020/September/5f63ef3c_why-switch-to-app-centric-microsegmentation-based-security/why-switch-to-app-centric-microsegmentation-based-security.png)

Being app-centric means shifting the focus away from individual VMs and their network identity to the applications themselves. Doing this application-based segmentation decouples policy from the network, simplifying policy administration and management.

Microsegmentation, sometimes called east-west firewalling, is the concept of creating granular network policies between applications and services. Implementation of microsegmentation is a key part of a defense-in-depth strategy against modern datacenter threats by providing the next layer of defense beyond traditional perimeter firewalls.

Microsegmentation essentially reduces the security perimeter to a fence around each service or virtual machine. The fence can permit only necessary communication between application tiers or other logical boundaries, thus making it very difficult for cyber threats to spread laterally from one system to another. Therefore, compromising one tiny perimeter doesn’t automatically expose any other targets.

Making microsegmentation application-centric further streamlines security operations by enabling the ability to define high-level policies without needing details about the underlying infrastructure or network identifiers. Policy focuses on application tiers or groups and what types of communication are allowed.

This is an important distinction as it separates the policy and groups from more dynamic network identifiers like IP addresses. This significantly reduces the complexity typically involved in policy management. The responsibility for understanding the infrastructure or network connectivity is removed from the human policy writers and left to the virtualization platform, which always knows the information needed to automatically update the policy accordingly.

## Quiz: Protecting AHV VM Workloads: Microsegmentation & Flow

![](https://raw.githubusercontent.com/ARBUCHELI/HYBRID-CLOUD-ENGINEER-NANODEGREE-PROGRAM-/main/images/480.jpg)

## Nutanix Calm DSL

A domain-specific language (DSL) is a computer language specialized to a particular application domain. This is in contrast to a general-purpose language (GPL), which is broadly applicable across domains.

A general-purpose (GPL) language, from a usage point of view, can be described as deliberately missing features that are specific to a product or technology. With that in mind, they are therefore much better suited to working with a broad-range of technologies. Some examples of general-purpose languages could be HTML (markup), Python (programming), and C# (programming).

On the other hand, you can think about a DSL as a way of simplifying programming tasks that are specific to a domain or product. In this case, the Nutanix Calm DSL, as suggested by the name, is specifically written to work with the Nutanix Calm product. It won’t interact with an operating system from the perspective of writing a custom application and it certainly won’t create a dinner recipe.

![](https://video.udacity-data.com/topher/2020/September/5f63ef66_nutanix-calm-dsl/nutanix-calm-dsl.png)

DSL offers all the richness of the Calm UI, but with the additional benefit of being human readable, with version controllable code that can handle even the most complex application scenario.

For example, entities like Services, Packages, Substrates, Deployments, and Application Profiles, which form the building blocks of a blueprint, can be defined as Python classes. Users can specify their attributes as class attributes, and neatly define actions on those entities (procedural runbooks) as class methods. Calm DSL can also accept native data formats such as YAML and JSON, allowing reuse into the larger application lifecycle context of a Calm blueprint.

## Runbooks

![](https://video.udacity-data.com/topher/2020/September/5f63ef92_runbooks/runbooks.png)

Calm Runbooks helps orchestrate automation tasks across infrastructure and applications in a hybrid cloud infrastructure. Runbooks provides users with an easily scalable way to orchestrate tasks outside the lifecycle management already enabled by Calm blueprints.

A Runbook is a collection of orchestration tasks defining “What to do” and “Where to do it.” Calm Runbooks support shell/PowerShell commands, variables, HTTP requests, delay, loops, and decision tasks, among other existing Calm constructs.

By their very nature, Runbooks are agnostic to the application grouping, and use an endpoint such as a hostname or IP address and port, or a URL, to run against. To make them truly versatile, Runbook tasks can run on VMs, applications, and categories. And to help you get started with Runbooks, Calm’s task library comes pre-seeded with over 200 ready-to-use tasks.

Runbooks can be triggered both manually by end-users, based on role-based access, or hooked up via REST APIs to monitoring and service-desk tools for automated execution.

A good example of where Runbooks are useful is for upgrades or patch management. Previously, tasks such as patching a critical vulnerability across hundreds of database instances was hard to do via blueprints, as you would have to patch each instance of the application. Runbooks simplify life cycle management across hundreds of application instances, or shared resources, which cut across the application layer and apply to multiple groups of infrastructure components.

## Quiz: Nutanix Calm DSL and Runbooks

![](https://raw.githubusercontent.com/ARBUCHELI/HYBRID-CLOUD-ENGINEER-NANODEGREE-PROGRAM-/main/images/481.jpg)

## Working with Prism Central APIs

### Nutanix REST API Explorer
As part of Nutanix’s software-defined environment, Nutanix provides a vast array of interfaces allowing for simple programmability and interfacing.

Nutanix REST APIs allow you to create scripts that run system administration commands against the Nutanix cluster. The API enables the use of HTTP requests to get information about the cluster as well as make changes to the configuration. Output from the API calls are returned in JSON format. The REST API exposes every capability and data point of the Prism UI and allows for orchestration and automation within the Nutanix framework.

A utility called the REST API Explorer is available within Prism to help you get started with using the REST API. The Explorer displays the parameters and format for the API calls that can be included in scripts. Sample API calls can be made to show the type of output you should expect to receive.

### Accessing the Nutanix REST API Explorer
There are multiple ways to access the REST API Explorer, depending on which interface you happen to be working with at the time.

If you’re in Prism, simply click the Admin menu and select REST API Explorer from the list of options.

![](https://video.udacity-data.com/topher/2020/September/5f63efbf_access-rest-api-explorer-1/access-rest-api-explorer-1.png)

If you’re viewing Calm, click the question mark icon at the bottom left corner of the screen. In the About Nutanix Calm popup that appears, click the REST API Explorer link.

![](https://video.udacity-data.com/topher/2020/September/5f63f039_access-rest-api-explorer-3/access-rest-api-explorer-3.png)

### OpenAPI/Swagger
When you search for OpenAPI, you’ll often see the terms OpenAPI and Swagger used interchangeably. While it isn’t strictly true now, this wasn’t always the case.

What is now known as the OpenAPI Specification began life as the Swagger Specification in early 2010. It was created by Tony Tam, who was working at an online dictionary company named WordNik. In 2015, the Swagger Specification was acquired by SmartBear Software, which created a new organization called the OpenAPI Initiative, sponsored by the Linux Foundation.

In January 2016, the Swagger Specification was renamed to the OpenAPI Specification — and that has been its name ever since. Now, ‘OpenAPI’ is used to mean the specification itself, while ‘Swagger’ refers to some of the most popular tools used to implement the specification.

### What is OpenAPI?
The Open API Specification is a format that you can use to describe the entirety of a REST APIs, including endpoints and endpoint operations, authentication methods, licenses, terms of use, and more.

### What is Swagger?
Swagger is a set of open-source tools that allow you to use the OpenAPI Specification to work with REST APIs. As per their documentation, the major Swagger tools include:

* Swagger Editor, a browser-based editor where you can write OpenAPI specs
* Swagger UI, which renders OpenAPI specs as interactive API documentation
* Swagger Codegen, which generates server stubs and client libraries from an OpenAPI spec

## Quiz: Working with Prism Central APIs

### QUIZ QUESTION
What is the difference between OpenAPI and Swagger?

* OpenAPI is the set of open source tools built around the Swagger Specification.

## Exercise: HTTP Task for APIs

![](https://raw.githubusercontent.com/ARBUCHELI/HYBRID-CLOUD-ENGINEER-NANODEGREE-PROGRAM-/main/images/482.jpg)
![](https://raw.githubusercontent.com/ARBUCHELI/HYBRID-CLOUD-ENGINEER-NANODEGREE-PROGRAM-/main/images/483.jpg)
![](https://raw.githubusercontent.com/ARBUCHELI/HYBRID-CLOUD-ENGINEER-NANODEGREE-PROGRAM-/main/images/484.jpg)
![](https://raw.githubusercontent.com/ARBUCHELI/HYBRID-CLOUD-ENGINEER-NANODEGREE-PROGRAM-/main/images/485.jpg)
![](https://raw.githubusercontent.com/ARBUCHELI/HYBRID-CLOUD-ENGINEER-NANODEGREE-PROGRAM-/main/images/486.jpg)
![](https://raw.githubusercontent.com/ARBUCHELI/HYBRID-CLOUD-ENGINEER-NANODEGREE-PROGRAM-/main/images/487.jpg)
![](https://raw.githubusercontent.com/ARBUCHELI/HYBRID-CLOUD-ENGINEER-NANODEGREE-PROGRAM-/main/images/488.jpg)
![](https://raw.githubusercontent.com/ARBUCHELI/HYBRID-CLOUD-ENGINEER-NANODEGREE-PROGRAM-/main/images/489.jpg)

## Exercise Solution - HTTP Task for APIs

Please watch the videos to follow the tutorials:

[![IMAGE ALT TEXT](https://github.com/ARBUCHELI/HYBRID-CLOUD-ENGINEER-NANODEGREE-PROGRAM-/blob/main/images/422.jpg)](https://www.youtube.com/watch?v=ZpZVI8K9nRI&feature=emb_logo)

[![IMAGE ALT TEXT](https://github.com/ARBUCHELI/HYBRID-CLOUD-ENGINEER-NANODEGREE-PROGRAM-/blob/main/images/422.jpg)](https://www.youtube.com/watch?v=f7yB4gYMqxc&feature=emb_logo)

[![IMAGE ALT TEXT](https://github.com/ARBUCHELI/HYBRID-CLOUD-ENGINEER-NANODEGREE-PROGRAM-/blob/main/images/422.jpg)](https://www.youtube.com/watch?v=2A5gpA_AySM&feature=emb_logo)

[![IMAGE ALT TEXT](https://github.com/ARBUCHELI/HYBRID-CLOUD-ENGINEER-NANODEGREE-PROGRAM-/blob/main/images/422.jpg)](https://www.youtube.com/watch?v=kUo6UyvUc4k&feature=emb_logo)

## Glossary

### Configuration drift: 
Refers to active configurations diverging from the configuration that was originally tested, approved, and deployed. Configuration drift is largely the result of manual processes, since these changes usually involve an actual person connecting to the server to make changes.

### Configuration management:
A category of software that can be considered the next generation of scripting.

### Continuous delivery:
A software engineering practice that involves keeping code in a state in which it is ready to deploy at any given time.

### Continuous deployment:
A software engineering practice that Involves the frequent, automated release of code to production.

### Continuous integration: 
A software engineering practice that involves multiple developers merging their individual code changes into the main repository as frequently as possible, usually multiple times a day.

### Continuous operations:
A software engineering practice which involves ensuring that IT operations are non-disruptive to users.

### Domain-specific language (DSL): 
A computer language specialized to a particular application domain. You can think of a DSL as a way of simplifying programming tasks that are specific to a domain or product.

### General-purpose language (GPL): 
A computer programming language which is broadly applicable across domains.

### Immutable infrastructure:
A system that does not change after deployment. This means that no updates, patches, or configuration changes are made to production systems. If changes are needed, a new version of the architecture is built and deployed into production.

### Lift and shift:
The most common strategy for migrating workloads among datacenters, infrastructure providers, hypervisors, clouds (or even from physical to virtual machine, or from virtual machine to container), which is done through storage conversion.

### OpenAPI Specification: 
Formerly called the Swagger Specification, the OpenAPI Specification is an API description format for REST APIs.

### Push button environments:
This refers to changing your existing, brownfield workloads (which have a lot of hard-coded configuration, data, and state in them) to push-button simplicity for new workload instances.

### Runbook:
A collection of orchestration tasks defining what to do and where to do it.

### Swagger:
A set of open-source tools built around the OpenAPI Specification that can help you design, build, document and consume REST APIs.

## Lesson Conclusion

* Congratulations! You’ve completed a major piece of this course and are one step closer to achieving your Hybrid Cloud Engineer Nanodegree.

* In this lesson, we discussed:

* Your role in evaluating infrastructure providers and avoiding lock-in, as well as tools and resources that you can use to move workloads between clouds

* The pets vs. livestock view of infrastructure, since DevOps requires that your material resources be distributed, fungible, and ephemeral

* How thinking about push button environments, configuration management, and automation across hybrid and multi-cloud deployments are pushing organizations further down the path towards agility

* The rise of immutable infrastructure (as configuration management begins to wane in popularity) and the benefits it offers to a business

* Four key concepts that you may have heard before in the context of DevOps — continuous integration, delivery, deployment, and operations

* Advanced Calm features, such as Windows alternatives to Linux and various associated components, and the options available to you when working with Prism Central APIs

In the next lesson, we’ll take a deep dive into the public cloud — specifically Amazon Web Services — and various features that you need to be familiar with to extend your blueprint into the public cloud. We’ll also compare and contrast those features with equivalent capabilities in your Nutanix Private Cloud, so you understand how these various components are analogous to each other. And then, you’ll spend some hands-on time with your blueprint in order to begin the work needed to change it from a private cloud-based application to a hybrid one.


________________________________________________________________________________________________________________________________________________________________________________



# LESSON 2 WORKING WITH A PUBLIC CLOUD INFRAESTRUCTURE PROVIDER

## Lesson Overview

Welcome to the lesson, Working with a Public Cloud Infrastructure. In this lesson, we will discuss one of the industry’s giant public cloud infrastructure providers, Amazon Web Services - often referred to as “AWS”.

We will start the lesson by covering an overview of public cloud. We will cover the various challenges consumers faced during initial days of adoption and see how these challenges have been overcome in the recent days. At the end of that topic, we will explain how an effective blend of multiple cloud services can help businesses be more agile to adapt to changing business needs.

We will then introduce you to AWS. We will cover what AWS is and also introduce you to some of the common AWS services. We will explain one of the popular AWS services, called the Amazon Elastic Compute Cloud (EC2). We will use EC2 as an example to explain various features associated with AWS. These features are used by many other services available on AWS as well.

We will also introduce you to terminologies such as instance, instance type, AMI, etc. We will relate these terms to Nutanix concepts to help you understand them better.

We will then cover the other major aspect of public cloud that was initially considered as a threat. Security and governance have always been a great concern in adopting a public cloud environment. But cloud providers these days have advanced tools, services and technologies that provide enhanced security, and also serve various compliance and governance requirements.

We will present various governance and security features such as regions, availability zones, security groups, SSH key pairs, IAMs, VPC. Each of these features has been a contributor to an increase in customers’ trust in cloud services.

By the end of this lesson, you will be familiar with several different AWS features, such as creating an Amazon account, picking a region for your account, and configuring all the security features that VPC, IAM, SSH key pairs and security groups. And, since the goal of this course is to extend your blueprint to the public cloud, we will also cover how to configure AWS as a provider in a Calm project environment.

## Big Picture

A cloud experience should generally be similar across different providers, but each will have particular differences in terminology and implementation. In the <strong>Modern Private Cloud Infrastructure</strong> course, we outlined the progression from IaaS to PaaS to SaaS offerings. When dealing with a public cloud provider, you will be able to choose from various data centers in different regions of the world, anchoring you to the local capabilities of the region. Generally, while most public cloud facilities are available in all regions, they may have different costs and potential limitations.

In the <strong>Public and Hybrid Cloud Management</strong> course, we will focus on just adding one public cloud provider: the leader of the industry, Amazon Web Services (AWS). We will add AWS as a new Calm provider and then enable it in your project. Then we will augment our three-tier web app blueprint to become a hybrid cloud web tier across both public and private cloud IaaS.

## Developing Your Intuition

We'll explore governance in AWS public cloud with IAM, then VM, OS Image, and SSH keypair properties of EC2, just as we did with Nutanix AOS and AHV.

Here's a map:

![](https://raw.githubusercontent.com/ARBUCHELI/HYBRID-CLOUD-ENGINEER-NANODEGREE-PROGRAM-/main/images/490.jpg)
![](https://raw.githubusercontent.com/ARBUCHELI/HYBRID-CLOUD-ENGINEER-NANODEGREE-PROGRAM-/main/images/491.jpg)

## Public Cloud Overview

Let us begin the lesson by a quick overview of what public cloud is. Public cloud is a cloud service offered by a third party cloud provider. In public cloud, you will be sharing the resources with other customers and will have no visibility on where your data is hosted. The customer can use the cloud services for free or pay for what they use, based on the service they choose. Some of the common public cloud providers are AWS, Microsoft Azure, Google Cloud Platform (GCP) and so on.

Many organizations are using public cloud for two major benefits, lowers CapEx and increases scalability. It eliminates the cost involved in buying, configuring, and maintaining an infrastructure. Public cloud eliminates the need to buy additional hardware to adapt to unpredictable workloads. With public cloud, you can simply add more servers and storage when required and release them required.

### Initial Challenges of Public Cloud
Even though organizations have increasingly used public cloud for their low cost and flexibility, there were challenges that cloud providers faced during the initial days of public cloud. Let’s look at those challenges.

![](https://video.udacity-data.com/topher/2020/September/5f63f782_challenges-of-public-cloud/challenges-of-public-cloud.png)

### Poor Connectivity
Internet bandwidth during initial days of cloud adoption was definitely a challenge in certain regions. With poor connectivity, organizations struggled to get access to their resources. Even though the best of infrastructure was provided by cloud providers, with poor internet connectivity the resources became near useless. Now, we have come a long way from what it was before. Internet bandwidth has evolved tremendously in certain regions, although some regions still continue to struggle.

### Loss of Control
Back then there were specific tools to access or integrate with the cloud environment. The tools to manage the on-premises datacenter and the cloud remained isolated. Public cloud remained like an island of inaccessible resources. Today, a huge number of tools exist in the market that help you to seamlessly manage and connect your environment with the cloud.

### Lack of Trained Staff
When the cloud was new, there was a lack of trained professionals who could understand the concept of cloud and implement that into their business. Lack of knowledge resulted in poor management and adoption of cloud. Today, cloud is no longer a new term, and is ingrained in our daily routine. There are also many trained and certified professionals that help organizations manage and adopt public cloud. The growth of cloud has also led to increased demand for cloud administrators and cloud architects.

### Security with public cloud
Security was the biggest concern of adopting a public cloud model. According to recent trends, we can see that people are willing to trust the public cloud and it is evident with massive growth in adoption of Office 365 or use of Amazon Web Services.

With increased adoption people have realized that public cloud is not meant to serve as a threat to sensitive information. Industry’s prominent public cloud providers now have various features to secure your information. Further in this lesson we will explore many such security and governance features available for AWS.

Thus, by choosing the right provider for your requirement you can still continue to run sensitive workloads on public cloud.

### Adapting to any cloud
Although there are multiple services provided by cloud providers these days, it is not a great strategy to run all your workloads on resources from a single cloud provider. If a provider goes out of business or increases pricing, you must be able to move quickly. You should always have a way to support any cloud, at any time .

Multi-cloud can be a great idea. This ensures that you aren't primarily dependent on a single provider. Building an interconnected web of clouds, you make it easier to protect yourself if you must make a quick jump from one of your providers.

## Quiz: Public Cloud Overview

### QUESTION 1 OF 2
Select the three primary challenges that the customers faced during the initials days of public cloud adoption?

* Poor connectivity

* Lack of trained staff

* Loss of control

### QUESTION 2 OF 2
True or False: Cloud providers now have advanced tools and services to enhance security in public cloud.

* True

## Understanding Amazon Web Services

### Understanding AWS

As mentioned previously, AWS is the industry’s leading public cloud provider. In this lesson, we will explore various features provided by AWS. Let’s start with a quick introduction to AWS.

Amazon Web Services, as the name suggests, is a set of various Amazon cloud services that can be accessed over the web/internet. These services are available for a variety of domains that range from compute, storage, network, database, to even security and identity compliance.

To explore the list of services, simply visit the AWS website and click the services dropdown. You can see a list of domains in alphabetical order and when you hover over it, you can explore all the services available for that domain. Shown here is an example of services available under analytics.

![](https://video.udacity-data.com/topher/2020/September/5f63f7b4_understanding-aws/understanding-aws.png)

Let’s briefly explore some of the services available under a few domains:

### Compute Services

* EC2, Elastic Cloud Compute, is a compute service for your applications.
* AWS Lambda is another unique and interesting cloud compute service where you pay to simply run your code. This eliminates the need to purchase a computing platform to run and test your code.

### Storage Services

* EBS, Amazon Elastic Block Store, is a block storage service that you can use with the EC2 compute service.
* Amazon Glacier is an archive storage solution that is extremely low cost and is usually used for compliance purposes.

### Security Services

* GuardDuty offers detection services against threats to protect your AWS accounts.
* Macie helps prevent data visibility to protect your sensitive data.

### Database Services

* Amazon RDS - This Database AWS service is easy to set up, operate, and scale a relational database in the cloud.
* Amazon DynamoDB is a fast, fully managed NoSQL database service.

Like this, AWS offers up to 175 services across multiple domains. We covered only a few examples in order to help you understand the plethora of services available. Both small and large-scale businesses can use a combination of these services to develop, deploy and test various applications without incurring the cost of owning the infrastructure/technology.

In this lesson, we will refer to one of the popular AWS offerings, Amazon EC2, to explain various concepts and features. Let’s start with what Amazon EC2 is.

### What is Amazon EC2?
As mentioned briefly earlier, Amazon EC2, Elastic Cloud Compute is a computing capacity available in the AWS cloud that eliminates the need to worry about your applications’ compute requirements. The word elastic in its name basically signifies that EC2 is an on-demand compute service that allows you to not only scale up, but also scale down to adapt to your changing application requirements. Also, you only pay for what you use.

This service eliminates the up-front investments in hardware and allows you to focus on your application performance for varying workloads.

Now, let’s dig a little deeper with this concept by exploring the two major elements of Amazon EC2.

### Instances

An instance is more like a virtual machine in the Nutanix environment. It is a virtual computing server running your applications on an Amazon EC2. Just like how a virtual machine consists of its own OS, software, and applications and so on. An instance will also include its own configuration and applications. Each instance works as a virtual private server.

### AMI

The instances are launched from a template called an AMI, Amazon Machine Image. AMIs are virtual appliances that are used to create an instance. Similar to the AHV image in the Nutanix environment, AMIs are basically images containing the configurations such as OS, app server and the applications. Just like how you use an image to create a virtual machine, you use an AMI to create an instance.

A single AMI can be used to launch multiple instances.

## Quiz: Understanding Amazon Web Services

![](https://raw.githubusercontent.com/ARBUCHELI/HYBRID-CLOUD-ENGINEER-NANODEGREE-PROGRAM-/main/images/492.jpg)

## Free Tier: t2.micro and t3.micro

### Free Tier
We just covered a brief overview of what AWS is. Now, let’s explore how you can use a few AWS services to explore its functionalities and capabilities without actually paying for the service.

Amazon provides various services for free to get hands-on experience on the AWS platform. This is called the free tier.

As shown in the picture below you can filter the free tiers by product or tier type and identify the ones that would like to explore and learn more.

![](https://video.udacity-data.com/topher/2020/September/5f63f7f6_free-tier-t2micro-and-t3micro-image-1/free-tier-t2micro-and-t3micro-image-1.png)

Free tier services have different limits. A few of these offers are always free. Some have a 12-month limit, and a few are available on a trial basis. Some services, such as AWS EC2 and Amazon RDS, have a monthly cap that can be used for 12 months.

For example, let’s consider the most common and frequently used service, AWS EC2 free tier. An AWS EC2 free tier includes 750 hours of Linux usage and 750 hours of Windows usage per month for 12 months. You can use these hours as per your requirement. To elaborate, you can use 1 Windows and 1 Linux instance for 750 hours every month or 12 Windows and 12 Linux instances for 75 hours every month.

![](https://video.udacity-data.com/topher/2020/September/5f63f814_free-tier-t2micro-and-t3micro-image2-/free-tier-t2micro-and-t3micro-image2-.png)

### t2.micro and t3.micro
t2.micro and t3.micro are a free tier instance type available when creating an instance. Before we explain what t2.micro and t3.micro are, let’s first understand what an instance type is.

### Instance Types
As mentioned previously, instances are like VMs and AMI are images used to create those VMs. Instances can be configured with various sizes and configurations. An instance type defines the hardware configurations used for an instance.

Amazon provides a variety of instance types, with each instance type providing different combinations of processor, memory, and storage capabilities that caters to various use-cases.

The instance types in Amazon EC2 are classified into five categories.

* General purpose: A1, T3, T2, M5, M5a, M4, T3a
* Compute optimized: C5, C5n, C4
* Memory optimized: R5, R5a, R4, X1e, X1, high memory, z1d
* Accelerated computing: P3, P2, G3, F1
* Storage optimized: H1, I3, D2

These instance types are available in various sizes. These sizes are nano, micro, small, medium, large, xlarge, 2xlarge, 4xlarge, 8xlarge, and so on.

### Example

For example, C4, C5, and C5n are different instance types available in the compute optimized category. C4 is available in five different sizes that include c4.large | c4.xlarge | c4.2xlarge | c4.4xlarge | c4.4xlarge.

### T2 and T3 instance types
T2 and T3 are general-purpose instance types that provide burstable CPU performance. General category instance type is used for a wide range of workloads that don’t specifically have compute/memory/storage optimization requirements.

T2 provides baseline level CPU performance with ability to burst beyond baseline level when required. They are charged on an hourly basis. T2 is widely used for websites and web applications, development environments, build servers, code repositories, and so on.

T3 are next generation instance types that can also burst beyond baseline but for as long as you need and whenever you want. These are widely used in micro-services, low-latency interactive applications, small and medium databases, virtual desktops, and so on; T3 uses AWS Nitro system and high frequency Intel xeon scalable processors. Compared to T2, T3 provides up to a 30% price performance improvement.

t3.micro and t2.micro are free tier instance types that are available in Amazon EC2 free tier. As mentioned earlier, in this free tier, you can use 750 hours of a t3.micro/t2.micro Linux instance and 750 hours of a t3.micro/t2.micro Windows instance per month for 12 months.

Both of these instance types work by collecting CPU credits during idle time and utilizing them when there is a spike.

A single AMI can be used to launch multiple instances of different types. These instance types differ by their compute, storage, and memory capabilities. Using a single AMI, you can also launch multiple instances of the same type.

## Quiz: Free Tier: t2.micro and t3.micro

### QUIZ QUESTION
What is an instance type?

* An instance type helps in defining the hardware configurations used for an instance.

## EC2 Regions and Availability Zones

Data locality is another primary concern that haunts multiple customers when hosting data on public cloud. Customers did not want their proprietary or sensitive workload to be stored on clouds whose data centers were not hosted in their local region, as this would result in non-adherence to their compliance and governance requirements.

They wanted their workloads and data to be running in the geographical region to which the data belonged in order to meet the local government compliance. This was especially crucial for the finance, banking, and government sectors.

In order to address this, it is important that the cloud provider has datacenters or clusters of datacenters running in a wide range of geographical areas to meet customers’ cloud requirements across the globe.

### Regions
Amazon cloud computing resources are hosted in different geographical locations across the world. These physical geographical locations are termed as regions.

Each region is completely independent from the other. The resources are very specific to a given region and are not replicated across different regions.

An Amazon account is used to decide the regions that are accessible to the user. This enables customers to meet proprietary and compliance requirements for any region. For example, the Amazon account holders in China can only access Beijing and Ningxia regions. Another example of compliance is AWS GovCloud. This cloud is accessible only using the AWS GovCloud account.

AWS provides a broad and increasing number of regions to cater to customer requirements across the globe. Multiple AWS regions are present in regions such as North America, South America, Europe, China, Asia Pacific, South Africa, and the Middle East.

They have around 24 geographical regions with around 77 availability zones across the globe.

New to availability Zones? Let’s understand what an availability zone is.

### Availability Zones
Within each region, there are multiple, isolated sub sections of regions called availability zones. Unlike regions, availability zones are connected and are dependent within a given region. Multiple availability zones ensure redundancy in order to failover to a new availability zone during a failure. Availability zones are connected using a high bandwidth, low-latency network in order to be able to synchronously replicate across availability zones. The communications between Availability zones are encrypted to secure data during transmission.

Availability zones are ensured to be at least 60 miles away from each other in order to be able to restore during a disaster. Multiple Availability zones in a single region results in high availability. This enables customers to run their applications in a fault tolerant environment.

For example, you can design your application to be distributed across multiple availability zones. In scenarios where an availability zone fails, the application can still function on the other availability zones.

Each region has a code of its own. An availability zone is represented by using the region code followed by a letter identifier. For example, us-east-2 is the region code for US East (Ohio) and an availability zone can be us-east-2a.

When launching an instance, you have the option to specify an availability zone for that instance. If you don't specify an availability zone, AWS will choose an instance based on the system health and available capacity. You can also migrate an instance from one availability zone to another based on your requirement.

![](https://video.udacity-data.com/topher/2020/September/5f63f87c_availability-zone/availability-zone.png)

### Identifying the regions available for your AWS account
You can find out the regions available for your account either using the AWS console or command line.

To find the AWS regions using the AWS console, simply select the regions dropdown at the corner of the screen. The regions available for that account are listed in the dropdown.

You can also see a dashboard of your resources in a given region on the EC2 dashboard.

![](https://video.udacity-data.com/topher/2020/September/5f63f89d_ec2-regions-and-availability-zones-image1/ec2-regions-and-availability-zones-image1.png)

### Identifying the availability zones available for your AWS account
Using the AWS console, Open the Amazon EC2 console. Select EC2 Dashboard on the navigation pane.

Under Service health, Zone status, you can view all the availability zones available for your amazon account.

![](https://video.udacity-data.com/topher/2020/September/5f63f8be_ec2-regions-and-availability-zones-image2/ec2-regions-and-availability-zones-image2.png)

## Quiz: EC2 Regions and Availability Zones

### QUESTION 1 OF 2
What is the benefit of multiple availability zones?

* Redundancy

### QUESTION 2 OF 2
True or False: Availability zones are isolated from each other and are not connected.

* False

## Amazon Machine Images

We have briefly touched upon what an AMI is in the previous section. Let’s do a quick recap and explore further.

AMIs include all the necessary information/configurations required to launch an instance. To launch an instance, you will have to specify an AMI and the instance type.

An AMI consists of three things:

* Snapshots of EBS or a template for the root volume of the instance: We will explore this further when covering the process to create an AMI.
* Permissions: Permissions to authorize users to use the AMI to launch instances.
* A block device mapping: This mapping connects the volume to the instance.

There are two types of AMI. You can either create your own AMI or use the available AMIs in the marketplace. The Amazon marketplace contains several different varieties of built-in AMIs with commonly used configurations that are readily available for use. For example, you have a Ubuntu AMI to run a Ubuntu instance or a windows-based AMI to run a Windows instance. For common uses, built-in AMIs enable you to quickly deploy an instance and start working on your development.

Next, let’s see the cycle of processes that an AMI goes through.

### Lifecycle of an AMI
Each AMI goes through a cycle of creation, usage and a delete cycle.

You can create an AMI and register in the AWS community. Once they are registered, you can use those AMIs in either of two ways:

* You can launch an instance from the AMI.
* You can copy the AMI to the same or different region for reuse.

The launched instances can further be customized and stored as another AMI.

![](https://video.udacity-data.com/topher/2020/September/5f63f914_ami-lifecycle/ami-lifecycle.png)

Note that to launch an instance from AMI, you must have launch permission from the AMI owner.

If you no longer require an AMI, you can erase the AMI from the marketplace by deregistering it. Deregistering an AMI does not affect the instance created from them.

### Creating your own AMI
Here we will be covering the process of creating a Linux-based AMI. For windows-based AMI refer to the AWS documentation.

There are 3 ways to create a linux-based AMI using an existing AMI.

* Using an Amazon EBS-backed AMI
* Using an instance-store-backed AMI
* Using an image builder

The root storage device of the instance is used to determine the process to create an AMI. So, before we explore these two processes, let’s understand what a root storage is.

Every instance has a root storage volume. The root storage volume has an image that includes all the necessary information to boot an instance during its launch. This root storage volume can either be an Amazon EBS (Elastic Block Storage) volume or an instance store volume.

You can determine the root storage volume of an AMI by looking at the description of an AMI. The reference ebs indicates Amazon EBS-backed AMI and instance store indicates an instance store backed AMI.

### Using an Amazon EBS-backed AMI
Consider a scenario where you want to configure multiple instances that include specific configurations. You then come across an Amazon EBS-backed AMI in the AWS marketplace that more or less meets your required configuration but might need a few customizations. In that case, you can simply use that AMI to launch an instance, customize the instance as per your requirement, and save the customized AMI. You can then use the custom AMI to launch multiple instances to use the updated configuration.

An AMI consists of a snapshot of the EBS root volume. When an instance is launched the snapshot is used to create an EBS root volume for the instance.

![](https://video.udacity-data.com/topher/2020/September/5f63f946_using-an-amazon-ebs-based-ami-2/using-an-amazon-ebs-based-ami-2.png)

This was just an example. For you to reuse and customize an AMI, they don’t necessarily have to be in the AWS marketplace. It can be any AMI that you can access but remember that the root volume has to be an Amazon EBS volume.

### Using an instance-store-backed AMI
The process to create an instance-store-backed AMI is very similar to using the Amazon EBS-backed AMI. Here you identify an instance store backed AMI and launch an instance from it. Customize it as per your requirement and bundle the volume. Bundling a volume is a time-consuming process. A bundle comprises an image manifest and files that include the template of the root volume. Then, upload the bundle to the Amazon S3 bucket and register it. You can then use the registered AMI to launch multiple instances.

![](https://video.udacity-data.com/topher/2020/September/5f63f95e_using-an-instance-stored-based-ami/using-an-instance-stored-based-ami.png)

When a new instance is launched using the newly created AMI, a root volume is created using the image file of the root volume in Amazon S3.

Whenever more instance volumes are added to the instance, the block device mapping of both, the new AMI and the instance, contains information about the newly added volumes.

### Using an image builder
You can create any AMI (Windows or Linux based) using an image builder. Using an image builder along with AWS VM Import/Export (VMIE), you can not only create an AMI but also other formats such as vmdk, vhdx, ovf, etc.

An image builder is used to make the image building process easier and faster. EC2 image builder is a service used to create, maintain, store, and deploy Windows and Linux based images for Amazon EC2 and on premise. The images created from the EC2 image builder can be pre-installed and pre-configured with software and settings to meet specific IT requirements.

An image builder consists of an image pipeline. An image pipeline defines the process of customizing the images. It consists of the image recipe, build components, infrastructure configuration, distribution, and test settings. An image recipe is a document that specifies all components and tests applied to the source image to create an image with the required configuration. The source image is the image selected and the OS for which the customizations are applied.

![](https://video.udacity-data.com/topher/2020/September/5f63f9b3_image-builder/image-builder.png)

The process to build an image using the Image Builder include:

* Selecting the source image: An existing AMI or a snapshot of EBS volume.
* Creating an image recipe: You add components to create an image recipe for your image pipeline. Components are the building blocks that are consumed by an image recipe, for example, packages for installation, security hardening steps, and tests. The selected OS and components make up an image recipe.
* Output: An image in the required output format is created.
* Distribute: The image can then be distributed across AWS Regions after it passes tests in the image pipeline.

There are various processes associated with an AMI like selling an AMI, buying an AMI, etc. These processes are out of the scope for this course. If you want to know more refer to the links in the further research section.

## Quiz: Amazon Machine Images

### QUESTION 1 OF 3
True or False: a single AMI can be used to launch multiple instances of different instance types.

* True

### QUESTION 2 OF 3
What happens to the instances created from an AMI, when an AMI is deregistered?

* It does not affect the instances created from that AMI.

### QUESTION 3 OF 3
What does an AMI consist of? Select the 3 options that apply.

* Snapshot of EBS or a template of the root volume of an instance
* Permissions
* Role mappings

## Security Groups

Despite its flexibility and low costs, security has been a primary concern for organizations that host data on the public cloud. Many companies have faced security threats, hijacks, and data breaches by not using adequate security measures to save sensitive information on the cloud. Today, cloud providers have multitudinous features and technologies that enable you to safeguard the data on cloud services.

Amazon includes close to 230 security, compliance, and governance services and features that help customers breathe a sigh of relief and focus on innovation. From this topic onwards, we will explore various such features that AWS provides in order to not only protect the information but also ensure that authorized users have access to it.

### What are security groups
A security group is a network security feature that enables you to control the incoming and outgoing traffic from an instance. Security groups provide protection at the instance level.

Think of security groups as a firewall. Just like how a firewall gauges the incoming and outgoing traffic, the security groups enable you to control the IP addresses, protocols, and ports that can be used to reach an instance. This is done by defining rules for a security group. You can assign different rules to each security group based on your requirement. An instance is assigned with one or more security groups.

![](https://video.udacity-data.com/topher/2020/September/5f63fa0a_security-groups/security-groups.png)

During the launch of an instance, you can specify one or more security groups. When an incoming traffic arrives at an instance, an Amazon EC2 evaluates all rules associated with all the security groups of an instance. This evaluation decides whether to allow the incoming traffic.

### Security Rules
As mentioned earlier security rules define the traffic that’s allowed to reach an instance and the traffic that’s allowed to exit an instance.

![](https://video.udacity-data.com/topher/2020/September/5f63fa30_security-groups-image1/security-groups-image1.png)

When you create a security group, it consists of two tabs, inbound and outbound. You can use each of these tabs to specify security rules for incoming and outgoing traffic. Here is what a security rule consists of:

* Name: A name to the security rule.
* Protocol: TCP, UDP, or ICMP.
* Port range: Single or range of port numbers to be allowed.
* Source(inbound) or destination(outbound): The source and destination IP addresses allowed for an instance.
* Description: Acts as an identifier to the rule.

In this section, let’s look at some of the properties of a security group rule and then explore what a security group rule consists of.

* By default, all outbound traffic is allowed inside a security group. Thus, using rules, you can restrict the outbound traffic to only the specified IP addresses.
* You cannot create rules to restrict traffic but can only specify rules to admit traffic.
* When a rule is modified, the changes are applied automatically to all the instances associated with a security group.
* If an instance sends a request, the outgoing traffic for that request and the incoming response traffic is allowed irrespective of the security rules.
* When multiple security rules are assigned to an instance, all rules are accumulated to form a large set. This huge set is evaluated by Amazon EC2 to determine access to an instance.

Let’s explain this further with an example.

![](https://video.udacity-data.com/topher/2020/September/5f63fa57_security-groups-image2/security-groups-image2.png)

Consider an instance with a security group that has an inbound rule to allow traffic from an device IP address XX.XX.XX.XX on port 22 and an outbound rule to allow all outgoing traffic.

When an incoming traffic from the device with public IP address XX.XX.XX.XX reaches the security group, it is allowed to reach the instance using port 22. This is because the devices’ port and public IP address is mentioned in the security rule of the instance. But, when a device with an IP address YY.YY.YY.YY tries to reach the instance using the same port 22, the traffic is restricted. This is because, during evaluation, the EC2 instance did not find the public IP address YY.YY.YY.YY in the inbound rule. Thus, for an incoming traffic to communicate to the instance all incoming security rules have to be passed.

You can see from the diagram that all outbound traffic is allowed to pass through the security group.

Inorder to track the incoming and outgoing traffic of an instance, security groups use connection tracking. But there is an exception. Not all traffic is tracked. For example, when a request is sent from an instance. The outgoing request is tracked as a new entry but the incoming response to the request is not tracked. For more information, refer to the connection tracking section in the Amazon EC2 security groups.

### Types of Security Groups
There are 2 types of security groups, default, and custom security groups.

### Default security group

Every Amazon account includes one default security group in a given region. If not explicitly specified, every instance uses the default security groups containing default security rules.

A default security group is identified with the name default. The default security rules of the default security group are:

* Allows all incoming traffic from the other instances associated with the default security group.
* Allows outgoing traffic from the instance.

You can add or remove security rules for a default security group but cannot delete a default security group.

### Custom security group

If you have specific requirements in mind, you can create your own security groups with custom rules. You can then associate this security group to an instance during its launch.

By default, when you create a security group, it allows no incoming traffic and allows all outgoing traffic. You can modify this later once associated with an instance.

### Creating a Security Group
You can create a security group using Amazon management console (old and new), or command line. Here we will cover the process using the new console.

* Browse to Security Groups.
* Click Create security group.
* Enter a name and description
* Select the VPC (For now, think of VPC as the network used to connect to the cloud).
* Add security group rules.
* Click Create.

### Creating a Security Group Copy
A security group cannot be copied across regions. You can use the copy feature to replicate a security group and make further customization without having to create one from scratch.

To create a copy of the security group:

* Browse to the security groups section.
* Select the security group.
* Click Copy to new security group, from the Actions dropdown menu.
* Click Create.

### Adding rules to a Security Group
You can add inbound and outbound rules to a security group.

### Adding an inbound rule

To do add an inbound rule,

* Select the security group.
* Click Edit inbound rules from the Actions dropdown.
* Click add rules.
* Choose a type and source. Enter a description.
* Save the rule.

In the source section, you have three options.

* Custom: This option allows you to specify specific IP addresses from which you want to allow the incoming traffic.
* Anywhere: This allows all incoming traffic.
* My IP: This option you will only allow communication from your personal computer by specifying its public IPv4 address.

### Adding an outbound rule

The process is very similar to adding an inbound rule, simply select Edit outbound rules from the Actions dropdown.

Instead of selecting the source, here you will have an option to select the destination from which you can allow the outbound traffic. You have the same three options: custom, anywhere and my IP. Configure as per your requirement and save the settings.

You can use the same process to edit the inbound and outbound rules.

### Web server and Database Server Security Rules
When configuring security rules, you need also consider the purpose of the instance. As this influences the type of security rule you define.

For instances that run as web servers, the inbound rules have to allow all traffic from HTTP and HTTPS access from any IP address. For example, you have to add an inbound rule with port 80 and 0.0.0.0/0 as source IP to allow all inbound traffic from any IPv4 address.

For instances that run as database servers, you must configure the security rule with the appropriate port number and add the range of IP addresses that you can allow for incoming traffic. For example, you have to configure an inbound rule with port 1433 to enable access to a Microsoft SQL Server database.

Similarly, you can configure outbound traffic to restrict all outbound traffic and only allow access to the internet for software upgrades. You can do this by adding outbound rules to add port 80 and specifying the source IP accordingly.

## Quiz: Security Groups

### QUIZ QUESTION
Which below are the two default security rules for the default security group?

* Allows all incoming traffic from the instances associated with the default security group.

* Allows all outgoing traffic from the instance.

## SSH Key Pairs

SSH key pairs are used to authenticate a user to access a linux instance. It is an added security feature that lets you use key pairs to login to the instance. Just like how Calm enables you to use SSH key pairs from RSA for Linux systems, Amazon also supports the use of SSH key pairs.

Key pairs are security credentials required to login to your instance. The word ‘key pair’ in its name signifies that there are two keys that work hand in hand to authenticate a user. For Linux systems, the public key encrypts the login information and the private key is used to remotely connect to the instance using SSH. In AWS, the public key is stored in Amazon EC2 and the private key is stored by the user. Private key is unique and confidential to a given instance. Anyone who knows the private key can access an instance. So, ensure that the private key is kept confidential.

You are allowed to specify an instance key pair when you launch an instance. During the launch, you have the option to either choose an existing key pair or create a new one. When an instance boots for the first time, the public key is placed in ```~/.ssh/authorized_keys``` under your instance entry. You will have to enter the private key to login to your instance.

Remember that the private key is not stored anywhere in EC2 and there is no way to recover a private key in case you forget it.

### Creating a keypair
As mentioned previously you can use an existing key pair or create a new one in order to use SSH to login to your instance.

You can create a key pair using one of the following interfaces:

* New console
* AWS CLI
* Old console
* PowerShell

We will cover the process using the new console.

* Open the Amazon EC2 console.
* Browse to Network and Security, choose Key Pairs.
* Enter a name and select the file format.
* Click create key pair.

The keys that Amazon EC2 uses are 2048-bit SSH-2 RSA keys. The private key file is downloaded by your browser. Ensure to save it in a safe place. The file will have the name and format you specified.

In case you are using a MacOS or a Linux system, execute the following command to set read permissions of your private key. If this process is not done, then you cannot connect to your instance using the key pair.

```chmod 400 my-key-pair.pem```

![](https://video.udacity-data.com/topher/2020/September/5f63fa8a_creating-a-ssh-keypair/creating-a-ssh-keypair.png)

### Importing the public key to Amazon EC2
In this case, you would use an existing key pair by importing the public key to the EC2. Let’s look at the process in more details:

When you already have a key pair, ensure to save the private key in a secure place and the public key in your local drive.

* Open the Amazon EC2 console.
* Browse to key pairs.
* Enter a name.
* Import the public key either by uploading the file or pasting the public key.
* Choose Import key pair.

![](https://video.udacity-data.com/topher/2020/September/5f63fab7_importing-a-ssh-pair/importing-a-ssh-pair.png)

### Retrieving the public key for a key pair
You can retrieve the public key for a key pair using the following command.

```ssh-keygen -y -f <path to private key>```

You can also retrieve it using the instance metadata file. Refer to the AWS documentation on key pairs for more details.

### Replacing a key pair
There may be situations where someone has access to the private key or you might want to restrict access to the user having the private key. In these situations, you can replace the key pair and this prevents the user from accessing the instance.

To do this:

* Create a new key pair.
* Connect to the instance with the existing key pair.
* Open the .ssh/authorized_keys file and replace the public key information with the new public key.
* Disconnect and reconnect to the instance with the new key pair.

## Quiz: SSH Keypairs

### QUESTION 1 OF 2
In AWS, where are the public and private keys stored?

* The public key is stored in Amazon EC2 and the private key is stored in a location of the user’s choice.

### QUESTION 2 OF 2
True or false: You can recover a private key if lost or forgotten.

* False

## IAM

Identity and Access Management is a topic we had covered in the previous course. For a quick recap, IAM is a feature used to control access to the resources. Just like how you use role-based access control (RBAC) to provide customized access to Prism, similarly Amazon uses IAM to create roles and provide access permissions to access the AWS resource. Identity means authenticating the user and access management means authorizing that the users with the appropriate access are allowed to perform operations on the resources. IAM helps in ensuring that the right people have the right access to the AWS resources.

Security groups and keypairs provide instance level security, whereas IAM provides account level security to the AWS environment. Using IAM, you can create users, groups, and roles with custom access permissions to manage your resources.

When you create an Amazon account, you will be the root user of that account and also have all access permissions to all resources and services. If this account is managed by an organization running a huge number of instances and various services, administering all the services, analytics, storage consumption and security can be a cumbersome task. Thus, you may want to offload some of the responsibilities to a few administrators or business groups but also simultaneously be able to control the level of access for each of these users/groups. IAM enables you to create multiple users and groups to provide custom access permissions to the resources. This way you add multiple users to your account without compromising on security.

For example, you can create a user group to provide admin access to all your storage services. You can even be more granular and create a user group with admin permissions to only access a specific S3 bucket.

### User, groups and roles
There are three types of users in IAM.

* Root user
* IAM user
* Federate user

We mentioned root users previously. Root user is the owner of the Amazon account. A root user has all access permissions to all resources in an Amazon account. A root user can create IAM and federate users.

As discussed earlier, instead of using the root account for all tasks, you can create IAM users within your account in order to delegate tasks to various other users or business groups. You can authenticate an IAM user using a password or separate keypairs to login to the environment. When logged in, the IAM user will only have access to resources for which he has permissions.

If there is already a set of users and groups created outside the AWS, you can federate those user identities into your AWS account. The users authenticated in this mechanism are called federated users.

You can apply access permissions either to an individual user or to a group. When permissions are added at the group level, any new user added to the group will have permissions assigned to that group.

### Creating a group and adding a IAM user
IAM consists of its own console. Using IAM you can configure IAM users, groups and roles. Here we will cover the process of creating a group and adding a IAM user in a Linux instance.

From the IAM console,

* Browse to Groups.
* Click Create New Group.
* Enter a name.
* Attach a policy that defines permissions.
* Click Create group.

To add users, browse to Users

* Click Add Users.
* Enter the username.
* Configure the access type.
* Select the user group to add.
* Click Create user.
* Click Save.

### How does IAM work
Let us next look at how IAM works:

There are three primary elements involved when authenticating and authorizing a user. These are principal, request and AWS resources.

![](https://video.udacity-data.com/topher/2020/September/5f63faf6_iam-image1/iam-image1.png)

A “principal” can be any user or application that requires access or needs authentication and authorization to perform an action on an AWS resource. AWS resources can be any asset that a principal needs access to perform an operation or an action.

For a principal to perform an action on the AWS resource, it sends a ‘request’ to AWS. AWS collects the information provided in the request as a request context to analyze and authorize the request.

A request consists of:

* Actions or operations: This can be as simple as starting an instance or as sensitive as changing the password.
* Resources: The AWS resource can be a user, an Amazon EC2 instance or even an Amazon S3 bucket on which the principal would like to perform an action.
* Principal: The principal can be a user or an application sending the request. This information helps AWS to evaluate the permission associated with the principal.
* Environment data: This includes data such as time, user agent, SSL enabled status, etc.
* Resource data: This can be additional data regarding the resource such as a tag for Amazon S3 instance.

The authentication and authorization happens before sending a request to AWS. A principal must be an identified user/application with the required permissions to send a request to an AWS resource.

The authentication method depends on the principal making a request. A root user uses the Amazon account email ID and password to authenticate. Whereas an API uses the access and secret key to sign in.

If a principal authentication fails the request will automatically be denied. If a principal authentication succeeds, AWS then uses the request to authorize the action.

During authorization, AWS evaluates the request context created to process all policies associated with that request. Even if one of those policies associated with a request denies the action, the entire request will be denied. There are different types of policies. The policies evaluated during authorization depend on the type of request. If the request is to grant permissions to a resource, then identity-based policies are evaluated to check access permissions for a user. If a principal needs access to a resource, the resource-based policies are evaluated to check whether the principal is mentioned in the policy.

The evaluation logic for any request in an AWS account is as follows:

* All requests are denied by default.
* Any exclusive allow permissions override the default.
* Any organization security control policies or session policies overrides the allow permissions.
* You can even exclusively deny permissions. If a policy contains a deny, it overrides all allow permissions.

Once the principal is authenticated and the request is authorized, the request is approved to perform the action or operation on the AWS resource.

### Accessing IAM
IAM can be access in one of the following 4 ways:

* AWS management console
* AWS command line tools
* AWS SDKs
* IAM HTTPS API

### Use case
One of the primary used cases of IAM is multi factor authentication (MFA). As the name says its multiple levels/factors to authenticate a user. IAM is used in scenarios, where you would like to add an extra layer of security to your assets.

When you enable MFA, you will use the username and password to login to your user account. This serves as the first factor of authentication. Once you enter the username and password, you will also be prompted to authorize using a virtual MFA device. This serves as the second factor of authentication.

This way even if the password is leaked, the user will not be authenticated as the second factor of authentication cannot be passed.

## Quiz: IAM

![](https://raw.githubusercontent.com/ARBUCHELI/HYBRID-CLOUD-ENGINEER-NANODEGREE-PROGRAM-PART-2/main/images/493.jpg)

### QUESTION 2 OF 2
True or False: AWS collects the information provided in the request as a request context to analyze and authorize the request.

* True

## VPC

### Virtual Private Cloud (VPC)

Virtual Private Cloud or VPC is a feature in AWS that provides service level security to your AWS resource. Virtual Private Cloud is a service where you can provision and launch an isolated section of Amazon Web Services using a virtual private network defined by you. This way you can implement the network infrastructure similar to an on-premises datacenter, but with the benefit of a scalable infrastructure. To compare and contrast, in an Amazon EC2 service, the internal and external IP addresses are assigned by Amazon; in a VPC, the internal IP, and external IP addresses are defined by the customer.

Imagine VPC as your own datacenter in the cloud that can be accessed only by the network defined by you. VPC is separated from the other networks used to connect to the cloud.

If Amazon EC2 becomes the compute layer, then VPC will be the network layer of your infrastructure. A few AWS services that can be used by Amazon VPC are Amazon EC2, Amazon RDS, Amazon Route S3, and so on.

The network configurations that you can define for your Amazon VPC include defining the IP addresses, subnets, network gateways, and so on. You can increase security by including security groups to the instances in your subnets.

### Accessing VPC
You can create and access VPC using the AWS management console, AWS CLI, AWS SDKs, and Query API.

### How does a VPC work
If you are new to networking, here are a few terms you must know before we move further.

* VPC: Basically, a virtual network to your Amazon account.
* Subnet: A range of IP addresses that you could use to connect to the VPC.
* Internet Gateway: A gateway in your VPC to enable communication between the VPC and internet.
* Routing table: Rules that define the route to your network traffic.
* NAT Gateway: A gateway that allows instances in the private subnet to connect to the internet but not allow the internet to initiate a connection with the instance.

Each VPC can have a range of IPv4 addresses that can be used for its communication. A VPC spans across all availability zones in a given region to provide availability. You can define one or more subnets within a VPC. A subnet is one or more range of IP addresses used to connect to the VPC. A subnet cannot span across multiple availability zones and should be within a single availability zone.

You can configure 3 types of subnets in a VPC:

* Private subnet
* Public subnet
* VPN-only subnet

![](https://video.udacity-data.com/topher/2020/September/5f63fb42_subnet-types/subnet-types.png)

Private subnets are used for instances to communicate with each other within a subnet. Private subnets can only have private IP addresses.

For instances to be able to communicate with the internet, the subnet must have a public IP address or an elastic IP. For now think of elastic IP as a static public IP address that an instance can have. We will explain elastic IP further in this lesson. The subnet must then be connected to an internet gateway. An internet gateway enables an instance to connect to the internet.

If you want to enable your instance on the Amazon EC2 to connect with your on-premise network. The subnets in the VPC and the internal on-premise network must be connected to a virtual private gateway. The subnet connected to a virtual private gateway is called a VPN-only subnet. This type of connection is called AWS site to site VPN.

Subnets group the instances but it is the routing table that decides the route in which a traffic is directed. Every VPC comes with a default routing table to manage traffic across all subnets in the VPC. Every subnet must be associated with at least one routing table for it to decide how an incoming or outgoing traffic be directed within and outside a network. Each routing table consists of many rules called routes that specify the destination and a target for a traffic.

Let us next understand the different types of VPCs. There are 2 types of VPC, default VPC and non default VPC.

Default VPC is a VPC that comes with your Amazon account by default. You also get a default subnet along with the default VPC. If you do not want to use a default VPC and prefer creating one of your own. It is called non-default VPC.

![](https://video.udacity-data.com/topher/2020/September/5f63fb60_default-vpc/default-vpc.png)

As mentioned earlier, only a default VPC contains a default subnet. A subnet created for a non-default VPC and additional subnets created for a default VPC are called non-default subnets. You can use public subnets to connect resources within a VPC to the internet and private subnet to enable resources to communicate internally. VPC uses routing tables to direct traffic within and outside a subnet.

The advantage of a default VPC is that it helps you get started quickly. It is useful when you do not have specific requirements and it also eliminates the hassle to create and configure a VPC from scratch. You can use the default VPC and even make customizations to the existing configurations based on your need.

### Connecting to the internet
Now that you know what a default VPC is, let’s explore how a default and a non default VPC connect to the internet.

An instance launched in the default VPC comes with the public and private IPv4 addresses.

To connect your default VPC to the internet, you can use the default internet gateway. All traffic leaving the default VPC and reaching the internet passes through the internet gateway. Security groups are used to control communication at the instance level but the internet gateway is used to control traffic outside a VPC. An internet gateway enables your instances to connect to the internet through the Amazon EC2 network edge.

The instance launched in a non-default VPC only contains private IP4 addresses. You have to explicitly specify a public IP4 address for any instance from a non-default VPC to connect to the internet. Another way for a non-default VPC to connect to the internet is to change the subnet’s public address attribute.

### Use cases
One of the common use cases for VPC is hosting a multi-tier web application. Using VPC you can enforce strict security restrictions to your application. Consider an application with an application server, database server, and web server. Using VPC, you can host the web server in a public subnet and the application server and database server in a private subnet. This way you can restrict access to the application and database server. You can even control communications between these servers by using security groups and access control lists.

Another use case is moving your organization's application to the cloud without compromising on network security. With VPC, you can easily migrate your corporate applications to the cloud and use your existing VPN to connect to your applications. This way you do not have to change the way the users have been accessing the application. It also provides the added benefit of scalability. You can add compute and other necessary resources required to scale as per your need with complete control on the network.

The VPC concept is vast and a few topics are out of the scope of this course. If you want to know more on these topics, refer to the links in the further research section.

## Quiz: VPC

![](https://raw.githubusercontent.com/ARBUCHELI/HYBRID-CLOUD-ENGINEER-NANODEGREE-PROGRAM-PART-2/main/images/494.jpg)

### QUESTION 2 OF 2
For a given Amazon account, how many VPCs are available by default?

* 1

## Exercise: Set Up AWS

![](https://raw.githubusercontent.com/ARBUCHELI/HYBRID-CLOUD-ENGINEER-NANODEGREE-PROGRAM-PART-2/main/images/495.jpg)
![](https://raw.githubusercontent.com/ARBUCHELI/HYBRID-CLOUD-ENGINEER-NANODEGREE-PROGRAM-PART-2/main/images/496.jpg)
![](https://raw.githubusercontent.com/ARBUCHELI/HYBRID-CLOUD-ENGINEER-NANODEGREE-PROGRAM-PART-2/main/images/497.jpg)
![](https://raw.githubusercontent.com/ARBUCHELI/HYBRID-CLOUD-ENGINEER-NANODEGREE-PROGRAM-PART-2/main/images/498.jpg)
![](https://raw.githubusercontent.com/ARBUCHELI/HYBRID-CLOUD-ENGINEER-NANODEGREE-PROGRAM-PART-2/main/images/499.jpg)

## Exercise Solution - Set Up AWS

[![IMAGE ALT TEXT](https://github.com/ARBUCHELI/HYBRID-CLOUD-ENGINEER-NANODEGREE-PROGRAM-/blob/main/images/422.jpg)](https://www.youtube.com/watch?v=osFQu5GFSRg&feature=emb_logo)

[![IMAGE ALT TEXT](https://github.com/ARBUCHELI/HYBRID-CLOUD-ENGINEER-NANODEGREE-PROGRAM-/blob/main/images/422.jpg)](https://www.youtube.com/watch?v=azNmNKcLOgQ&feature=emb_logo)

[![IMAGE ALT TEXT](https://github.com/ARBUCHELI/HYBRID-CLOUD-ENGINEER-NANODEGREE-PROGRAM-/blob/main/images/422.jpg)](https://www.youtube.com/watch?v=a05CTelIAeE&feature=emb_logo)

## Elastic IP

Let’s consider an example to understand what an elastic IP address is and how it will be useful.

Consider that you have a website that communicates with an instance on AWS. This site uses the public IPv4 address of the instance to connect to it over the internet.

Every instance has a default public IPv4 address. This public IP address changes when an instance stops or restarts. Upon restart, the instance is dynamically assigned a new public IPv4 address from the Amazon pool of public IP addresses.

Now, in our scenario, if the instance fails and restarts, then the website will no longer be able to communicate with the instance. This is because the instance will now have a new public IP address and the website points to the old public IP address.

![](https://video.udacity-data.com/topher/2020/September/5f63fc6d_inelastic-ip/inelastic-ip.png)

Thus, to avoid such communication failures, you can use elastic IPs. Every Amazon account holder will have access to 5 default elastic IPs. You can allocate an elastic IP to the Amazon account and then associate it with an instance. Elastic IP is a static public IPv4 address that you can associate to an instance. An Elastic IP can be associated with only one instance at any time. If an elastic IP is assigned to an instance that already has a public IP address, then the public IP address is automatically dropped into the Amazon’s pool of IPv4 addresses.

So, in the scenario we mentioned earlier, the communication failure can be avoided using an elastic IP. During an instance failure, you can simply associate the elastic IP address to a new functional instance. This way the website pointing to the elastic IP will still be functional even if an instance fails.

If the failed instance is back online, you can again assign the elastic IP back to the first instance. This elasticity in assignment of public IP address results in continuous availability of the instance services.

Remember that even if you disassociate an elastic address, it is still assigned to your Amazon account until release.

![](https://video.udacity-data.com/topher/2020/September/5f63fb8d_without-elastic-ip/without-elastic-ip.png)

### Allocating an Elastic IP to your Amazon account
You can allocate the elastic IP address from two places.

* Amazon’s pool of public IP address
* Custom IP addresses bought for your Amazon account.

To allocate an elastic IP, from navigation page:

* Select the elastic IP
* Choose Allocate Elastic IP
* Select scope as either VPC or EC2-Classic.
* If you choose VPC, then select which public IP address pool you would like to choose.
* Click Allocate.

### Associating an Elastic IP to an instance
In the Elastic IP page,

* Select the Elastic IP.
* Select Associate Elastic IP address from the Action dropdown.
* Choose an instance in the resource type.
* Enter the instance name.
* Click Associate.

### Disassociating an Elastic IP from an instance
In the Elastic IP page,

* Select the Elastic IP
* Select Disassociate Elastic IP address from the Action dropdown.
* Click Disassociate

### Release an Elastic IP
An Elastic IP should always be associated with an instance. You will be charged for the unused elastic IP. To avoid this, you can release the elastic IP back to the pool. To do this:

* Select the Elastic IP.
* Select Release Elastic IP addresses from the Action dropdown.
* Click Release.

## Quiz: Elastic IP

![](https://raw.githubusercontent.com/ARBUCHELI/HYBRID-CLOUD-ENGINEER-NANODEGREE-PROGRAM-PART-2/main/images/500.jpg)

### QUESTION 2 OF 3
True or False: when an instance restarts, a new public IP address is allocated to the instance from the public IP address pool.
* True

### QUESTION 3 OF 3
How many elastic IP addresses are available by default for an Amazon account?
* 5

## AWS Limitations

Although AWS includes features that secure your workloads, there are a few limitations that you need to consider while hosting your data on cloud.

![](https://video.udacity-data.com/topher/2020/September/5f63fcd4_aws-limitations/aws-limitations.png)

### Transfer costs:
We covered how a few AWS services are charged based on the hours of usage in the Amazon free tier section. Know that, Amazon charges to transfer out of the AWS environment as well. For example, uploading a file to Amazon S3 is free, but downloading the same file to your on premise environment/local system has a cost associated with it. This cost varies based on the region in which the data is hosted on. You may also have to pay to transfer data between regions as well.

### Application refactoring:
When moving applications from one cloud environment to the other, the applications are usually re-architectured or a major amount of code is modified in order to adapt to the new environment. This process is called application refactoring. It is a time consuming process, as you have to modify the application without affecting the behavior and efficiency of it. Thus it is important to decouple your application from the underlying platform.

### Control on hardware: 
Although, there are several features and functionalities to ensure that applications on cloud are always available, still many organizations are not too sure when they want to host their mission critical application on a public cloud. Public cloud does not provide the ability to control the hardware parameter for mission critical workloads.

These limitations are actually considerations to keep in mind while architecting your cloud environment. Nutanix has products such as Nutanix clusters on AWS, Calm, and Beam that enables you to seamlessly work on applications both on-premise and on cloud.

Nutanix Clusters is a cloud platform that extends the simplicity and ease of use of its software to the public cloud. This eliminates the cost and management complexity of hybrid environments and enables seamless mobility across private and public clouds without any rearchitecting of the apps due to built-in networking integration with AWS. Nutanix clusters can be added and controlled from Prism Central. This makes Prism Central a single hybrid cloud control pane.

Nutanix Clusters help you decouple applications from the underlying platform, it also helps you decouple your business investments from the underlying platform. You have the freedom to use your portable Nutanix software licenses to the cloud of your choice. Calm as you know enables you to automate provisioning, scaling, and life cycle management of applications for the cloud. On the other hand, Nutanix Beam optimizes your resource allocation, reducing cloud costs.

## Quiz: AWS Limitations

### QUIZ QUESTION
What are the limitations of using AWS? Select the three limitations that we discussed in this topic.

* Application Refactoring

* Lack of control on hardware

* Transfer costs

## Exercise: Add AWS Provider

![](https://raw.githubusercontent.com/ARBUCHELI/HYBRID-CLOUD-ENGINEER-NANODEGREE-PROGRAM-PART-2/main/images/501.jpg)
![](https://raw.githubusercontent.com/ARBUCHELI/HYBRID-CLOUD-ENGINEER-NANODEGREE-PROGRAM-PART-2/main/images/502.jpg)
![](https://raw.githubusercontent.com/ARBUCHELI/HYBRID-CLOUD-ENGINEER-NANODEGREE-PROGRAM-PART-2/main/images/503.jpg)

## Exercise Solution: Add AWS Provider

[![IMAGE ALT TEXT](https://github.com/ARBUCHELI/HYBRID-CLOUD-ENGINEER-NANODEGREE-PROGRAM-/blob/main/images/422.jpg)](https://www.youtube.com/watch?v=PA4hy0OkNfg&feature=emb_logo)

[![IMAGE ALT TEXT](https://github.com/ARBUCHELI/HYBRID-CLOUD-ENGINEER-NANODEGREE-PROGRAM-/blob/main/images/422.jpg)](https://www.youtube.com/watch?v=NY-dsb6DqwI&feature=emb_logo)

## Exercise: Deploy to AWS

![](https://raw.githubusercontent.com/ARBUCHELI/HYBRID-CLOUD-ENGINEER-NANODEGREE-PROGRAM-PART-2/main/images/504.jpg)
![](https://raw.githubusercontent.com/ARBUCHELI/HYBRID-CLOUD-ENGINEER-NANODEGREE-PROGRAM-PART-2/main/images/505.jpg)
![](https://raw.githubusercontent.com/ARBUCHELI/HYBRID-CLOUD-ENGINEER-NANODEGREE-PROGRAM-PART-2/main/images/506.jpg)
![](https://raw.githubusercontent.com/ARBUCHELI/HYBRID-CLOUD-ENGINEER-NANODEGREE-PROGRAM-PART-2/main/images/508.jpg)
![](https://raw.githubusercontent.com/ARBUCHELI/HYBRID-CLOUD-ENGINEER-NANODEGREE-PROGRAM-PART-2/main/images/509.jpg)

## Exercise Solution: Deploy to AWS

[![IMAGE ALT TEXT](https://github.com/ARBUCHELI/HYBRID-CLOUD-ENGINEER-NANODEGREE-PROGRAM-/blob/main/images/422.jpg)](https://www.youtube.com/watch?v=r7rteHoDqDU&feature=emb_logo)

[![IMAGE ALT TEXT](https://github.com/ARBUCHELI/HYBRID-CLOUD-ENGINEER-NANODEGREE-PROGRAM-/blob/main/images/422.jpg)](https://www.youtube.com/watch?v=Zn3Lv9GvXSs&feature=emb_logo)

## Glossary

### Amazon EC2 - 
Amazon EC2, Elastic Cloud Compute, is a compute service for your applications.

### Amazon EBS - 
EBS, Amazon Elastic Block Store, is a block storage service that you can use with the EC2 compute service.

### AMI -
Amazon Machine Images (AMIs) are virtual appliances that are used to create an instance.

### Availability Zones -
Within each region, there are multiple, isolated sub sections of regions called availability zones.

## AWS - 
Amazon Web Service is a set of various Amazon cloud services that can be accessed over the web/internet.

### Free Tier - 
Amazon provides various services for free to get hands-on experience on the AWS platform called the free tier.

### IAM - 
Identity and Access Management (IAM), is a mechanism to control access to the resources using users, groups and roles.

### Instance - 
Instance is a virtual computing server running your applications on an Amazon EC2.

### Internet Gateway - 
An internet gateway enables an instance to connect to the internet.

### Key pair - 
A key pair consists of two keys that work hand in hand to authenticate a user. These are public key and private key.

### Principal - 
The principal can be a user or an application sending the request to access an AWS resource.

### Public cloud - 
Public cloud is a cloud service offered by a third party cloud provider. You will be sharing the resources with other customers and will have no visibility on where your data is hosted.

### Regions - 
Amazon cloud computing resources are hosted in different geographical locations across the world. These physical geographical locations are termed as regions.

### Root storage volume - 
The root storage volume has an image that includes all the necessary information to boot an instance during its launch.

### Rules - 
outing table consists of rules that define the route to your network traffic.

### Security groups -
A security group is a network security feature that enables you to control the incoming and outgoing traffic from an instance.

### Security rule - 
Security group rules define the traffic that’s allowed to reach an instance and the traffic that’s allowed to exit an instance.

### Subnet -
A subnet is a range of IP addresses that you could use to connect to the VPC.

### VPC - 
Virtual Private Cloud is a service where you can provision and launch an isolated section of Amazon Web Services using a virtual private network defined by you.

### t3.micro and t2.micro - 
t3.micro and t2.micro are free tier instance types that are available in Amazon EC2 free tier.

## Lesson Conclusion

To conclude, public cloud is evolving and many organizations have now been able to seamlessly run their workloads on public cloud. Although there were initial challenges such as poor connectivity, loss of control, and lack of trained staff, with improved technologies, public cloud has now been a feasible option for many small and large scale businesses.

In this lesson, AWS was our primary focus. We started the lesson by explaining AWS and also introduced you to various services. We then covered one of the most widely used services of AWS, which is Amazon EC2.

Amazon EC2 is a compute service used to run various virtual servers. These virtual servers are called instances. Instances can host applications and run OS and databases. Instances are created using an image called the Amazon Machine Image. Amazon Machine Image(AMI) contains all necessary configuration details required to launch an instance. A single AMI can be used to launch multiple instances. When launching an instance using an AMI, an instance type must be selected. The instance type defines the hardware configuration used to run an instance.

Amazon provides free hands on services, platforms, and products. This is called a Free Tier. T2 and T3 are free instance types available in the Amazon EC2 free tier.

In order to provide data locality, Amazon uses regions and availability zones. With multiple regions and availability zones you can now host workloads closer to the region in which the account is created. This feature helps in meeting the local compliance and governance requirements.

An EBS backed AMI contains a snapshot of EBS, permissions, and device mapping. We then covered 2 ways to create an AMI. We also explained the difference between these methods.

We then explore various security features such as security groups, key pairs, IAM, VPC and elastic IPs.

Security groups are firewalls used to control the incoming and outgoing traffic of an instance. Security groups use security rules to configure the inbound and outbound traffic. Security groups provide instance level security in the Amazon EC2 environment.

SSH keypairs are key pairs used to authenticate a user. It involves a public and private key. Public key is stored in EC2 and the private key is stored by the user.

IAM provides benefits very similar to the role-based access control (RBAC) in Prism. IAM provides a mechanism to control access to Prism and also create multiple users, groups and roles to manage the Amazon environment. We covered how an IAM works and also explored the steps to create an IAM.

We then covered what a Virtual Private Cloud is and how a VPC works. Virtual Private Cloud is the network security feature for your cloud. If EC2 is your compute layer then VPC is your network layer. VPC helps in providing complete control of the network connecting the cloud. This way you can achieve high standards of network security even on public cloud.

Elastic IP is a feature used to manage an instance failure. It eliminates the dependency on the dynamic public IP address of an instance.

With all these security features provided, public cloud is less vulnerable to security attacks and breaches. By implementing these features you can not only secure the environment at the cloud level but also at the instance level.

In the next lesson, we will cover how to implement a hybrid cloud scalability and deployment choices for a web application. We will also explore how to configure a hybrid web tier blueprint. We will discuss how to operate the load balancers across public and private cloud web tiers in a blueprint.

<strong>Note:</strong> All other brand and product names mentioned herein are for identification purposes only and may be trademarks of their respective holders.


________________________________________________________________________________________________________________________________________________________________________________



# LESSON 3 IMPLEMENTING HYBRID CLOUD SCALABILITY AND DEPLOYMENT CHOICE 

## Lesson Overview

Welcome to the lesson, Implementing Hybrid Cloud Scalability and Deployment.

In the previous lesson we dived deep into AWS so that you have a strong foundation for how the public cloud works - in the same way that we’ve talked about the private cloud in this course.

That was really the second piece of the puzzle. If you remember, Calm helps seamlessly orchestrate your workloads between on-prem infrastructure and your public clouds, like AWS. So, in this lesson, we will use your combined knowledge of both the public and the private cloud to discuss matters of scale - specifically, hybrid cloud scalability.

Now that you’re familiar with AWS, we’ll jump right into extending your blueprint into the hybrid cloud by talking about how you add an AWS provider to Calm.

Next we’ll move on to global load balancing - what it is, why it matters, the considerations involved, and what global load balancing looks like for different infrastructure providers.

We will also discuss the considerations involved when you need to think about how your audience will access your application - such as the nature of the application, VPNs, geographical considerations, network performance, and network and data locality.

And finally, we will recap a couple of concepts covered under application profiles, all of which you will need to keep in mind when scaling your application.

Let’s jump right in.

## Big Picture

The goal for effective scalability and deployment choices is to ensure tasks are managed in an efficient time-sensitive manner, as orchestrated in the blueprint, rather than in a manual, ad-hoc, reactive manner. In the <strong>On-Premises Private Cloud Automation</strong> course, you learned about some of the strategies that can be applied to Hybrid Cloud Management and had time to think about how those strategies apply to effective decision making.

By thinking about how applications and deployment strategies can apply for different, but related manners irrespective of the cloud environment running an application, it became apparent how planning these strategies can impact application lifecycles at later stages.

In essence, these strategic planning initiatives can help drive the adoption of application-specific technologies such as Cloud-Init for configuration automation and shell tasks for task automation, while also opening the door to considering domain-specific automation approaches such as the Nutanix Calm DSL and runbooks.

In previous lessons, the idea of domain-specific tools, typically locked to a single infrastructure provider, being not-so-desirable was discussed, although there is certainly a place for certain technologies that follow this pattern, if they can aid in improving application agility and lifecycle management. As an example, the Nutanix Calm DSL, when applied to Nutanix Calm specifically, won't apply to improving lifecycle efficiency in other products, but can allow some tasks that were otherwise repetitive and complex to be distilled down to a much similar approach. From another angle, the use of the Nutanix Calm DSL to automate runbook execution is an excellent way of streamlining the scalability and deployment decisions that are critical to this lesson.

## Developing Your Intuition

![](https://raw.githubusercontent.com/ARBUCHELI/HYBRID-CLOUD-ENGINEER-NANODEGREE-PROGRAM-PART-2/main/images/510.jpg)

In this lesson, we'll explore a number of ways that scalability and deployment decisions can be planned strategically and efficiently without sacrificing the domain knowledge that most automation engineers have spent so long to develop.

As an example, what happens when the web component of a web application requires additional resources? This lesson will demonstrate how this can be achieved quickly and efficiently, thereby avoiding the need for manual resource deployment.

## Adding an AWS Provider to Calm

Let’s begin by discussing how to add an AWS provider to Calm.

You must configure AWS as a service provider if you want to create and use a blueprint on AWS platform.

Before you begin, ensure that you have an AWS account with valid credentials. You must also have an IAM user account. The User account must have full EC2 access and IAM read-only access. Additionally have an access key ID and the secret access key for the IAM user account.

To configure AWS as a provider:

Click the settings icon
Click the Providers tab.
Provide details such as name, type, access key ID, secret access key, regions, and a public image.
Click Save
You can even click Verify to verify the entered credentials.

You can use the configured AWS provider when you create a blueprint for AWS.

If you want to configure an AWS C2S provider, refer to this link for more details.

![](https://video.udacity-data.com/topher/2020/September/5f63fe9d_configuring-aws-setting-calm/configuring-aws-setting-calm.png)

## Scalability and Global Load Balancing Considerations

Load Balancing, as you may remember from a previous course, is a system that distributes traffic across multiple resources, which are typically servers. When these servers are in geographically distributed datacenters, the act of distributing traffic between them is called Global Load Balancing.

![](https://video.udacity-data.com/topher/2020/September/5f63fec4_global-load-balancing/global-load-balancing.png)

Global load balancing is a very real, very practical scenario for a lot of businesses once they reach a certain size and scale. For high availability purposes, businesses simply cannot risk having all of their data, applications, and systems in a single physical location. A secondary datacenter, or multiple secondary datacenters, are set up to ensure business continuity and protect and preserve data in the event of a natural disaster or major failure.

Then, to fulfil jurisdictional, regulatory, or performance requirements, some businesses need to set up and operate multiple datacenters. As an example, to ensure data privacy under law, it may be necessary to keep European data in Europe. On the other hand, for performance reasons, it may be necessary to have the Asian arm of a business supported by one or more datacenters in Asia.

Either way, distributing and managing traffic on a global scale is ongoing, daily consideration for most businesses. However, as with all things in computing, solving problems at scale takes on an entirely new dimension, more so when that ‘scale’ is quite literally planet Earth.

Some considerations that you need to be aware of in the context of global load balancing are:

* When scaling up or down, global resources need to be scaled with demand, so extra apps, network load balancers, instances (VMs, AMIs, etc.) and even regions/geos need to be dynamically scaled.
* Automation, tagging, governance/compliance for security, management and reporting, etc. all have to scale up/down with the global resources listed previously.
* Basic infrastructure needs, such as public IPs, and DNS A/C/MX records, need to be modified as resources scale up or down.
* Data can be sharded and replicated for availability and access needs.
* Different cloud failover models apply: pilot light, A/B failovers (primary/secondary), cold/warm/hot failover models, or even “always-on” where session traffic is routed to surviving instances.

## Global Load Balancing Between Infrastructure Providers

Since global load balancing isn’t a new concept, infrastructure options are already available to you. However, when making this decision, you need to weigh the options that you have and choose the one that best suits your business’ and application’s requirements.

One of the first choices you’ll find yourself making is whether to invest time, effort, and other resources into public cloud load balancers, whether to use something open source like HAProxy, or whether to work with a different solution provider entirely such as F5. Then, when you’re making that decision, you also need to think about whether you want a hardware-based solution, which is what F5 offers, versus a load balancer service, which Cloudflare provides. And finally, you also need to consider how you want to load balance between clouds, at what layer you want to load balance, and why.

Ultimately, there is no right answer. The only answer that matters will be derived from your assessment of your infrastructure and business requirements, which will lead to an understanding of what works best for your specific situation. So, very quickly, let’s go over some of the global load balancer options that are available to you.

![](https://video.udacity-data.com/topher/2020/September/5f63ff53_load-balancer-options/load-balancer-options.png)

### AWS Elastic Load Balancer
Elastic Load Balancing (ELB) can be used with an Amazon ECS service to ensure that traffic is distributed evenly. ELB supports three types of load balancers: Application, network, and classic.

### Application Load Balancer
An Application Load Balancer makes routing decisions at the application layer, i.e., HTTP/HTTPS. It supports dynamic host port mapping, path-based routing, and is capable of directing requests to different ports on each container instance in a cluster.

### Network Load Balancer
A Network Load Balancer makes routing decisions at the transport layer, i.e., TCP/SSL, and is capable of handling millions of requests in a second. Like Application Load Balancers, Networking Load Balancers also support dynamic host port mapping.

### Classic Load Balancer
Functioning as something of a hybrid model, a Classic Load Balancer is capable of making routing decisions at either the application layer or the transport layer. However, a Classic Load Balancer needs a fixed relationship between the load balancer port and the container instance port. To ensure that this condition is met, your cluster will need at least as many container instances as the desired count of a single service that uses a Classic Load Balancer.

### HAProxy
HAProxy, which stands for High Availability Proxy is an open source load balancer and proxy server that is typically used for TCP and HTTP-based applications. It’s free, has become the standard for open source load balancing, and comes bundled with most Linux distributions. Since it’s a software-based load balancing solution, it balances requests using a variety of algorithms for server allocation.

### F5
Unlike the other load balancers we’ve discussed here, the F5 series of load balancers are hardware-based. That is, they are physical devices that distribute traffic across servers.

## Quiz: Global Load Balancing

![](https://raw.githubusercontent.com/ARBUCHELI/HYBRID-CLOUD-ENGINEER-NANODEGREE-PROGRAM-PART-2/main/images/511.jpg)

## Architecting for Access

When designing a greenfield application, the hybrid cloud engineer will have a multitude of choices available to filter through business requirements then additional technical, fiscal, and security concerns.

Access becomes a primary design criterion for security and hybrid cloud provider choice: who can access what and from where?

![](https://video.udacity-data.com/topher/2020/September/5f63ffd7_when-access-is-a-primary-design-criterion/when-access-is-a-primary-design-criterion.png)

A global audience for a web application typically requires access to a public front-end, but successive back-end functionality and supporting services, such as business logic, SaaS offerings, databases and other persistent storage should be protected from direct public access. Increasingly, mobile and desktop applications also require network access to reach back-end services. Private applications typically use the same architecture, but access can be restricted to corporate Local Access, Wide Area, and Virtual Private networks (LAN, WAN, VPN).

Variations of VPNs can be established between corporate networks and the private network address space of public cloud providers. For example, AWS Virtual Private Cloud (VPC) establishes IPsec network tunnels to “extend” the corporate data centers and private networks seamlessly to public cloud hosted services to satisfy corporate network access requirements. Of course, these public cloud hosted services must not be given public access in order to assure secure access.

Given that workloads can be placed anywhere, a hybrid cloud engineer should consult with network and security specialists to ensure access and geographic hosting considerations are addressed. Example requirements could include keeping customer information private and geographically constrained for data sovereignty or data may be transmitted globally in a secure fashion, but must be stored at rest on corporate owned and secured resources in a private cloud or on a highly audited public cloud.

Network performance also weighs on choosing where to place workloads, further driving the need for livestock fleets to be geographically distributed and placed as closely as possible to the customer. However, vastly distributed resources also place a network transit burden to reach supporting services as well as overhead to synchronize and replicate data between each cloud, which can have performance and cost implications.

Securing access while maintaining local access across hybrid, distributed resources can often create conflicting design decisions for a hybrid cloud engineer. Often these design decisions come down to network locality and data locality (sometimes also called data gravity). These decision points should be arbitrated by adhering to business requirements and working to bring any ambiguity or gap back to the business for resolution.

For this lesson’s exercise, the load balancer will remain on the private cloud for secure access. The hybrid web tier will be hosted on private cloud AHV and public cloud AWS. Both web tiers will need to access the database. It would be possible to allow AWS web tier access to a private cloud database via AWS VPC, but an easier design for this exercise will be to rehost the database on public cloud AWS and adjust AWS security groups to allow access from the Nutanix AHV cluster. The database must be available to all web servers, regardless of where they are hosted. Because of the ephemeral nature of your Nutanix AHV cluster outside of AWS, global network access must be granted for the database. Global access to a database is not a security best practice, but acceptable to simplify this learning exercise. A final warning: remember to delete your application workloads before leaving your session, your AWS resources will persist until explicitly terminated! If you forget to do so, your Nutanix resources will terminate automatically, but you will need to use the AWS web console to manually terminate AWS EC2 instances in your account.

## Exercise: Hybrid Web Tier

![](https://raw.githubusercontent.com/ARBUCHELI/HYBRID-CLOUD-ENGINEER-NANODEGREE-PROGRAM-PART-2/main/images/512.jpg)
![](https://raw.githubusercontent.com/ARBUCHELI/HYBRID-CLOUD-ENGINEER-NANODEGREE-PROGRAM-PART-2/main/images/513.jpg)
![](https://raw.githubusercontent.com/ARBUCHELI/HYBRID-CLOUD-ENGINEER-NANODEGREE-PROGRAM-PART-2/main/images/514.jpg)
![](https://raw.githubusercontent.com/ARBUCHELI/HYBRID-CLOUD-ENGINEER-NANODEGREE-PROGRAM-PART-2/main/images/515.jpg)
![](https://raw.githubusercontent.com/ARBUCHELI/HYBRID-CLOUD-ENGINEER-NANODEGREE-PROGRAM-PART-2/main/images/516.jpg)
![](https://raw.githubusercontent.com/ARBUCHELI/HYBRID-CLOUD-ENGINEER-NANODEGREE-PROGRAM-PART-2/main/images/517.jpg)
![](https://raw.githubusercontent.com/ARBUCHELI/HYBRID-CLOUD-ENGINEER-NANODEGREE-PROGRAM-PART-2/main/images/518.jpg)
![](https://raw.githubusercontent.com/ARBUCHELI/HYBRID-CLOUD-ENGINEER-NANODEGREE-PROGRAM-PART-2/main/images/519.jpg)

## Exercise Solution: Hybrid Web Tier

[![IMAGE ALT TEXT](https://github.com/ARBUCHELI/HYBRID-CLOUD-ENGINEER-NANODEGREE-PROGRAM-/blob/main/images/422.jpg)](https://www.youtube.com/watch?v=Atp0OZm0h-Q&feature=emb_logo)

[![IMAGE ALT TEXT](https://github.com/ARBUCHELI/HYBRID-CLOUD-ENGINEER-NANODEGREE-PROGRAM-/blob/main/images/422.jpg)](https://www.youtube.com/watch?v=plh2kjyHnH0&feature=emb_logo)

[![IMAGE ALT TEXT](https://github.com/ARBUCHELI/HYBRID-CLOUD-ENGINEER-NANODEGREE-PROGRAM-/blob/main/images/422.jpg)](https://www.youtube.com/watch?v=-0FRwO2768I&feature=emb_logo)

[![IMAGE ALT TEXT](https://github.com/ARBUCHELI/HYBRID-CLOUD-ENGINEER-NANODEGREE-PROGRAM-/blob/main/images/422.jpg)](https://www.youtube.com/watch?v=vO5Q-ThPkLE&feature=emb_logo)

[![IMAGE ALT TEXT](https://github.com/ARBUCHELI/HYBRID-CLOUD-ENGINEER-NANODEGREE-PROGRAM-/blob/main/images/422.jpg)](https://www.youtube.com/watch?v=RFBAUL8_VxM&feature=emb_logo)

## Exercise: Migrating Database Access

![](https://raw.githubusercontent.com/ARBUCHELI/HYBRID-CLOUD-ENGINEER-NANODEGREE-PROGRAM-PART-2/main/images/520.jpg)
![](https://raw.githubusercontent.com/ARBUCHELI/HYBRID-CLOUD-ENGINEER-NANODEGREE-PROGRAM-PART-2/main/images/521.jpg)
![](https://raw.githubusercontent.com/ARBUCHELI/HYBRID-CLOUD-ENGINEER-NANODEGREE-PROGRAM-PART-2/main/images/522.jpg)
![](https://raw.githubusercontent.com/ARBUCHELI/HYBRID-CLOUD-ENGINEER-NANODEGREE-PROGRAM-PART-2/main/images/523.jpg)
![](https://raw.githubusercontent.com/ARBUCHELI/HYBRID-CLOUD-ENGINEER-NANODEGREE-PROGRAM-PART-2/main/images/524.jpg)

## Exercise Solution: Migrating Database Access

[![IMAGE ALT TEXT](https://github.com/ARBUCHELI/HYBRID-CLOUD-ENGINEER-NANODEGREE-PROGRAM-/blob/main/images/422.jpg)](https://www.youtube.com/watch?v=CFSBbNVYWps&feature=emb_logo)

[![IMAGE ALT TEXT](https://github.com/ARBUCHELI/HYBRID-CLOUD-ENGINEER-NANODEGREE-PROGRAM-/blob/main/images/422.jpg)](https://www.youtube.com/watch?v=xq3Asp2tnDo&feature=emb_logo)

## Calm Application Profiles: Advanced

We have discussed application profiles in more detail in the On-Premises Private Cloud Automation course.

We had covered what an application profile is and also explained the best practices to follow when using an application profile. Let’s do a quick recap.

Calm enables you to extend your Nutanix infrastructure into the public cloud, like AWS. It provisions, scales, and manages infrastructure and applications across multiple environments to make the entire IT infrastructure more agile and application-centric.

Calm uses a construct called application profiles to enable you to create multiple profiles of different size and infrastructure. You can have one application profile with Nutanix as the underlying infrastructure and another with AWS. You can also have an application profile that is hybrid across multiple providers. This provides an IT operator with choice while deploying an application.

Another use for Application profiles is separate, but related application environments: a development web application deployment may use a development database password, while a staging environment could use a staging database password, and so on for each desired environment. In this manner, maximizing reuse for consistent governance and operations of the different application deployments from the same blueprint.




# Adaptation as a repository: Andrés R. Bucheli.
