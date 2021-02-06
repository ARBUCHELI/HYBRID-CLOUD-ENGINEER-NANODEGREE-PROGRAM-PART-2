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

## Quiz: Calm Application Profiles

### QUIZ QUESTION
Which Calm construct enables you to create multiple profiles of different size and infrastructure.

* Application Profiles

## Application Profiles Recap

Application profiles are one of the primary elements involved in building a Calm blueprint. You must select an application profile while you launch a blueprint. Application profiles expose simple choices to end users. Often these choices are about where an application should run (AHV or AWS), but they can also be about sizing (small or large), or a combination of the two (small AHV or large AHV or small AWS).

An application profile provides different combinations of the service, package, and VM while configuring a blueprint. The application profile also enables you to use the same set of services and packages on the different platforms.

Using application profiles, you can enable your application to be run in multiple ways. You can either change the size or change the infrastructure to deploy on. Any customization you have done can be reused or tailored on a per-profile basis.

## Quiz: Application Profiles Recap

### QUIZ QUESTION
What are application profiles?

* An application profile provides different combinations of services and profile variables while configuring a blueprint.

## Multiple Application Profiles

Every blueprint has a default profile, it can be thought of a base layer of the blueprint. The default profile was used in the single-VM blueprint, but it was invisible to the user.

If needed, the default profile can be renamed for a better description for operators. You can also create additional application profiles to cater to your requirement.

Additional application profiles provide the operator role (or higher) deployment choices when using an application deployment. This increases blueprint reuse (of actions and governance) instead of making separate blueprints for each permutation of deployment.

Use application profiles to reduce the amount of delegated run-time properties: less choice reduces complexity and increases productivity: less is more!

## Quiz: Multiple Application Profiles

### QUIZ QUESTION
How does using multiple application profiles benefit an operator?

* Provides deployment choices when using an application deployment.

## Application Profile Best Practices

### Application Profiles Best Practices
Let us next cover some of the best practices to follow when using an application profile.

### Naming an application profile

* When naming an application profile make it as simple and user-friendly as possible.
* Ensure to use nouns that reflect the audience use case or jargon. Capitalized noun, ideally without spaces. For example, UserAcceptanceTesting, QualityAssurance.
* Also make application profiles a set of mutually exclusive choices. This increases blueprint reuse and provides deployment choices when using an application deployment.
* Avoid overly context sensitive names that require previous knowledge when possible to allow the widest audience to understand each application profile and make the correct choice.

### Example use of profile for operator choice

* Recommended configurations, such as capacity size: small versus medium versus large resource consumption for different needs.
* Limited to full configuration delegation with run-time property overrides.
* Different infrastructure providers for a public, private, and/or hybrid deployment.

Overall, application profiles serve as a powerful tool to choose from any of a multitude of different hybrid cloud deployments.

## Quiz: Application Profile Best Practices

### QUIZ QUESTION
Select the 3 best practices that have to be followed when using application profiles.

* When naming an application profile make it as simple and user-friendly.

* Make application profiles a set of mutually exclusive choices.

* Ensure to use nouns that reflect the audience use case or jargon

## Exercise: Multiple Deployment Scenarios

![](https://raw.githubusercontent.com/ARBUCHELI/HYBRID-CLOUD-ENGINEER-NANODEGREE-PROGRAM-PART-2/main/images/525.jpg)
![](https://raw.githubusercontent.com/ARBUCHELI/HYBRID-CLOUD-ENGINEER-NANODEGREE-PROGRAM-PART-2/main/images/526.jpg)
![](https://raw.githubusercontent.com/ARBUCHELI/HYBRID-CLOUD-ENGINEER-NANODEGREE-PROGRAM-PART-2/main/images/527.jpg)
![](https://raw.githubusercontent.com/ARBUCHELI/HYBRID-CLOUD-ENGINEER-NANODEGREE-PROGRAM-PART-2/main/images/528.jpg)
![](https://raw.githubusercontent.com/ARBUCHELI/HYBRID-CLOUD-ENGINEER-NANODEGREE-PROGRAM-PART-2/main/images/529.jpg)
![](https://raw.githubusercontent.com/ARBUCHELI/HYBRID-CLOUD-ENGINEER-NANODEGREE-PROGRAM-PART-2/main/images/530.jpg)
![](https://raw.githubusercontent.com/ARBUCHELI/HYBRID-CLOUD-ENGINEER-NANODEGREE-PROGRAM-PART-2/main/images/531.jpg)

## Exercise Solution: Multiple Deployment Scenarios

[![IMAGE ALT TEXT](https://github.com/ARBUCHELI/HYBRID-CLOUD-ENGINEER-NANODEGREE-PROGRAM-/blob/main/images/422.jpg)](https://www.youtube.com/watch?v=fP2iD_Iu9kY&feature=emb_logo)


[![IMAGE ALT TEXT](https://github.com/ARBUCHELI/HYBRID-CLOUD-ENGINEER-NANODEGREE-PROGRAM-/blob/main/images/422.jpg)](https://www.youtube.com/watch?v=ZNRgR3fpyYA&feature=emb_logo)


[![IMAGE ALT TEXT](https://github.com/ARBUCHELI/HYBRID-CLOUD-ENGINEER-NANODEGREE-PROGRAM-/blob/main/images/422.jpg)](https://www.youtube.com/watch?v=mop4e6HmLi4&feature=emb_logo)

## Glossary

### Application Profiles - 
An application profile provides different combinations of the service, package, and VM while configuring a blueprint.

### Blueprint - 
A blueprint is the framework for every application that you model by using Nutanix Calm. Blueprints are templates that describe all the steps that are required to provision, configure, and execute tasks on the services and applications that are created.

### Calm - 
It provisions, scales, and manages infrastructure and applications across multiple environments to make the entire IT infrastructure more agile and application-centric.

### Services - 
Services are the virtual machine instances, existing machines or bare-metal machines, that you can provision and configure by using Nutanix Calm.

## Lesson Conclusion

And now we come to the end of this lesson. Before you move on to the next, let’s take a moment to recap everything that we talked about.

We used your knowledge of both the public and the private cloud to discuss hybrid cloud scalability.

Specifically, we spoke about:

* How you add an AWS provider to Calm.
* Global load balancing - what it is, why it matters, the considerations involved, and what global load balancing looks like for different infrastructure providers.
* The considerations involved when you need to think about how your audience will access your application - such as the nature of the application, VPNs, geographical considerations, network performance, and network and data locality.
* Concepts related to application profiles, all of which you need to keep in mind when designing multiple deployment scenarios with consistent governance and operations.



________________________________________________________________________________________________________________________________________________________________________________



# LESSON 4 HYBRID CLOUD FISCAL GOVERNANCE

## Lesson Overview

Welcome to the final lesson of the <strong>Public and Hybrid Cloud Management</strong> course, and the conclusion of the last course in the Hybrid Cloud Engineering Nanodegree program. In this lesson, we’re expanding our scope a little to products beyond Calm. We’ve already extended your blueprint into the public cloud, making it truly hybrid — but with the inclusion of the public cloud comes a collection of important considerations.

One of those, if you think back all the way to the beginning of this program, is cost. Because of the way the public cloud works, with the ability to either reserve resources or consume them on-demand, cost management can get quite tricky. There’s also an additional layer involved in managing your private cloud — the other half of your hybrid set up — and there’s a cost and consumption component there as well.

And, practically speaking, the hybrid model is only valuable if you’re able to manage it in a way that allows you to derive the benefits of cloud agility while controlling costs. If you’re running public cloud workloads, private workloads, and hybrid workloads where needed then you’ve achieved a true hybrid cloud model in which your applications are sitting wherever they work best.

A key challenge in public clouds is that the inherent agility and ease of use of public clouds leads to a consumption model in which you do not have control over how cloud resources are consumed. This can lead to inefficient consumption and costs can quickly spiral out of control. To control these costs, it is important to implement governance policies that determine how your cloud infrastructure is consumed and make adjustments for non-optimal consumption. So, quite simply, keeping an eye on and managing your costs is key. And to help you do that, we’re going to wrap this program up by talking about Xi Beam.

Beam is a Nutanix software-as-a-service product that helps customers with cost governance for both their public and private clouds. Beam’s cost optimization capabilities (called the cost optimization module) help identify cost saving opportunities in public clouds, and also enable financial governance across public and private clouds.

Beam’s cost optimization module helps provide visibility into multi-cloud spend across clouds such as AWS, Azure, and Nutanix. It comes with several features that provide an average of 35% or more in public cloud cost savings through elimination of unused resources, right-sizing of underutilized resources and purchase and exchange recommendations for reserved instances.

So, in a fair amount of detail, we’re going to discuss:

* How you can configure cost policies
* What you need to do to achieve public cloud cost savings
* How you can implement private cloud cost metering
* Using the chargeback mechanism to drive financial accountability
* Various reporting and alert capabilities that are available in Beam out-of-the-box

Thank you for making it this far in the course, and for sticking with us to the very end. Let’s begin.

## Big Picture

According to Gartner, “Cloud cost management is not just an operational concern. To be successful, it requires a tight collaboration among the disciplines of governance, architecture, operations, product management, finance and application development.

Focusing on efficient use of cloud services brings immediate and tangible financial benefits. Unfortunately, most organizations are unprepared to profit from this savings opportunity and they’re likely to overspend.” (Source: Gartner, Inc., How to Manage and Optimize Costs of Public Cloud IaaS and PaaS, March 2020)

For businesses adopting hybrid cloud architectures, this creates an unenviable scenario, managing IT costs and security across third-party cloud deployments. So what can Beam do to mitigate this?

![](https://video.udacity-data.com/topher/2020/September/5f65094a_big-picture-c3-l4-nutanix/big-picture-c3-l4-nutanix.png)

Beam further reduces complexity by providing users with deep visibility and rich analytics detailing how they are using the public cloud. It also provides rightsizing recommendations and detects cost anomalies based on machine intelligence along with one-click fixes so that IT teams can immediately optimize their cloud spend.

IT organizations get a clear view into the entirety of their public cloud deployments so unexpected cost leaks can be addressed before they turn into business challenges. Essentially, Beam helps organizations make continuous improvements with cost savings in mind when operating multi-cloud architectures.

Beam also provides out-of-the-box cost visibility into Nutanix private cloud resources (such as VMs, snapshots, files, etc.) using a built-in TCO model so that it’s easier to understand the true costs associated with Nutanix private cloud environments, as well as public cloud deployments.

Beam users can see how much they are truly spending on Nutanix resources while accounting for multiple cost factors such as hardware & software license costs, facilities costs, telecom cots, IT admin salaries, etc. — all within a single management dashboard based on a configurable TCO model.

And ultimately, this translates to a simple, unified global view that enables organizations to manage and optimize the cost of their entire IT infrastructure environment.

## Developing Your Intuition

Organizations today are increasingly adopting a multi-cloud architecture that spans across private and public clouds. This provides the necessary agility and flexibility of choice needed for IT teams to quickly fulfil business needs. However, with workloads spanning public and private clouds, there is a strong need for a cost governance solution that centralizes visibility across all clouds and implements cost governance policies to keep overall IT spending within budgets.

![](https://video.udacity-data.com/topher/2020/September/5f69339e_developing-your-intuition-nutanix-c4/developing-your-intuition-nutanix-c4.png)

### Summary of Challenges with Cost Governance in Adopting Multi-Cloud Architecture

Cloud cost governance is more complicated than ever. The lack of consumption controls especially in public clouds results in higher costs across the board. The number of choices available — both in terms of consumption models as well as number of services that each provider has — make purchasing decisions extremely complex. Also, the manual chargeback processes that most businesses have now are inefficient simply because the complexities of a multi-cloud system make granular, manual tracking a nightmare.

A key cost governance challenge in private cloud is the lack of immediate visibility into granular resource costs, as opposed to public clouds that provide a highly granular breakdown of cost of all cloud resources based on consumption.

There are also many different cost factors to consider, beyond simply the hardware and software infrastructure licenses, when it comes to evaluating the cost of owning and running a private cloud. Lastly, in order to drive financial accountability, IT Ops teams need the ability to chargeback spending to business units with a unified public and private cloud cost report.

So, in this lesson, we will discuss the various cost governance capabilities that Beam provides, including:

* Out-of-the-box visibility into private cloud resource costs
* Creating automated chargeback rules to allocate spending to the appropriate business unit
* Providing infrastructure right-sizing and purchase recommendations for public clouds that lead to deep cost savings

## Unifying Hybrid Cloud Cost Governance

It’s important to be able to compare costs across different cloud environments to optimize deployments. While this sounds simple enough, in practice these comparisons are often difficult.

For example, it’s impossible to know at a glance what on-premises VM configurations are good equivalents for an AWS t3.large or a 1.4xlarge instance. What AWS storage is the equivalent of your on-premises flash?

Without answers to these types of questions, it can be difficult to rightsize the infrastructure needed for workloads moving from one cloud to another, especially when you’re operating hundreds or thousands of VMs in each cloud.

![](https://video.udacity-data.com/topher/2020/September/5f6933dd_unifying-hybrid-cloud-cost-governance/unifying-hybrid-cloud-cost-governance.png)

You need some way to normalize cross-cloud comparisons to ensure you’re not comparing apples to oranges and making inaccurate decisions. It’s the only way to operate a hybrid cloud environment efficiently at scale.

Given these complexities, it’s perhaps surprising that the spreadsheet remains the most common tool for managing cloud costs.

And although the spreadsheet is the most common tool, it’s hardly the most appropriate. A more diligent application is needed for hybrid cloud cost governance. There are a number of tools that provide cloud cost management, yet according to the Flexera 2020 State of the Cloud report, just 33% of enterprises surveyed reported using them.

Your goal for cost governance should be to implement tools that provide cost governance across your private and public clouds deployments. This will provide a single point of management and optimization. The capabilities of the available tools vary widely, and each has its own strengths and limitations.

## Quiz: Unifying Hybrid Cloud Cost Governance

### QUIZ QUESTION
You are spearheading a project to deploy a number of new workloads, designed to meet the needs of various business-critical applications that your engineering team is working on. There are a variety of workloads involved — databases, applications, communications, and so on. The three options available to you are your private cloud, AWS, and Azure. Where should you deploy your workloads and why?

* It’s too early to say without a sizing and cost comparison. You need to look at each workload and determine the best fit — considering both performance and cost — before making a decision.

## Why Cost Governance is Critical for a Private Cloud

![](https://video.udacity-data.com/topher/2020/September/5f693408_why-cost-governance-is-critical-in-a-private-cloud-environment/why-cost-governance-is-critical-in-a-private-cloud-environment.png)

Cost governance has become a challenge for private cloud deployments. Cost overruns result from wasted or poorly utilized resources, and a lack of visibility into the true cost of private cloud resources. This, in turn, makes it impossible to accurately compare private cloud costs with public cloud costs for corresponding resources.

Private cloud users are often better at consuming resources than they are at releasing them, either due lack of visibility, mistakes, or neglect. To control usage and avoid wasting resources, you need to be able to monitor and meter the true costs of private cloud resources and be able to easily identify resources that are underused or abandoned.

A private cloud solution needs the ability to monitor, meter, and chargeback costs to end users and departments. Your private cloud should include granular cost metering that accounts for all contributing datacenter costs, enabling you to better predict future needs, plan for growth, and track costs and budgets.

## Understanding Cost Management in a Hybrid Cloud Environment

Things only get more complicated when you have workloads across multiple clouds — whether private, public, or hybrid. Jumping into the cloud affects your IT economic model, but jumping into more than one cloud makes the “cloud cost” question much more difficult to answer.

Financial comparisons between traditional data centers and cloud infrastructure are not simple to make. It is more than just comparing the compute, storage, and network costs between them. Many hidden overheads come into play and can become the deciding factor. There are several factors that you need to consider when determining ways to reduce costs.

![](https://video.udacity-data.com/topher/2020/September/5f693430_understanding-cost-management-in-a-multi-cloud-environment/understanding-cost-management-in-a-multi-cloud-environment.png)

### Vendor Discounts
Most cloud providers offer significant discounts when you pay the charges for computing resources upfront. For example, Amazon Web Services (AWS) provides “reserved instances,” which are typically compute and database services that are available at significant discounts if you commit to them for a duration of one year or longer. In this scenario, while you save on costs, you do lose the flexibility of being able to pay-as-you-go.

These reserved instances are usually available at discounts of 50–70 percent over on-demand pricing and are best used for production workloads or when you know that you will need that instance for an extended period.

Cloud vendors also offer their spare compute, storage, and network resources at a significantly discounted price-scheme called spot instances. For example, AWS sometimes offers its unused compute resources at discounts as high as 60–80 percent compared with on-demand pricing. These spot instances are perfect for dev/test workloads where you do not necessarily care about high availability and can work with whatever compute instance the cloud provider gives you.

In addition to reserved instances, AWS has announced the launch of Savings Plans which are expected to replace reserved instances in the long term. With AWS Savings Plans, you pay a discounted rate for a certain amount of compute capacity which can be consumed against any number and type of compute instances unlike reserved instances where you purchase reservation based pricing for a specific number and type of instances.

### Continuous Monitoring
Like the name suggests, optimal cloud management requires continuously monitoring resource utilization such as CPU, memory, disk usage, and so on. The purpose of continuous monitoring is two-fold. First, it ensures awareness of the cloud environment itself. And second, it ensures that cost anomalies at a user, service, or account level are detected and reported for remediation.

### Continuous Optimization
In order to avoid waste, cloud administrators should implement policies to resize resources that are too bulky for what they are being used for. For example, if you have a compute instance that is continuously using less than 2 percent CPU, you may be able to downsize it and save on costs without compromising performance.

### Leveraging Auto-scaling Tools
Most cloud providers offer auto-scaling tools that help you define usage limits and policies for various resources. These tools can automatically enforce your usage policy so that costs always remain within predefined limits.

### Automated Scheduling Policies
One of the biggest drivers of public cloud costs are zombie resources left running in the cloud that you may not be using anymore. For example, you may have compute and storage instances up and running 24/7 in your dev/test environment, but you may not need them overnight or on weekends. Why not use an automated scheduling policy that shuts them down when they are not needed and brings them up when you are ready to use them again? Turning off resources overnight and on the weekends can significantly add to your cloud cost reduction.

## Quiz: Hybrid Cloud Cost Management

You have been onboarded as a consultant to help a company reduce their cloud costs. After careful study of their public cloud and private cloud deployments, the IT team has worked out two ideas:

* a) Purchase reserved instances for their public cloud instead of using resources on-demand.
* b) Evaluate their on-prem workloads to determine if resources have been allocated effectively. If possible, scale resources down without impacting performance.

Which of these two suggestions should they move forward with?

### QUIZ QUESTION
Read the scenario above and determine which of the two options the IT team should move forward with.

* They should proceed with both options. Both approaches offer a viable path to cost reduction and optimization.

## Cost Optimization Solutions

### Elements of Cost Optimization Solutions

Jumping into the cloud affects your IT economic model, but jumping into more than one cloud makes the “cloud cost” question much more difficult to answer.

Financial comparisons between traditional data centers and cloud infrastructure are not simple to make. It is more than just comparing the compute, storage, and network costs between them. Many hidden overheads come into play and can become the deciding factor.

There are several factors that you need to consider when determining ways to reduce costs.

![](https://video.udacity-data.com/topher/2020/September/5f693472_elements-of-a-cost-optimization-solution/elements-of-a-cost-optimization-solution.png)

### Real-time Visibility and Analytics
Real-time visibility and analytics are critical in helping you see the areas where you may have too much or too little in the way of resources. Either condition can be costly, especially when system performance suffers and customers are inconvenienced.

Cloud Cost Management & Optimization (CCMO) tools use advanced machine learning to perform a timeseries analysis of the resource consumption log data to identify anomalous trends and usage patterns. The best CCMO tools can identify when cloud costs start to spike by looking for unexpected patterns in the billing data.

For example, you should look for which users are consuming which services in which region at what time of day. Anomalous deviations should be immediately flagged when the spending goes above a certain deviation from normal patterns. Machine learning-based automated cost anomaly detection can act as an early warning signal.

### Automated Budget Tracking and Chargebacks
Another feature you want in your CCMO tools is the ability to automate budget tracking and chargebacks. CCMO tools can help to optimize spending through budget tracking and chargeback by answering these questions:

* How much are you spending across your organization?
* Which team is spending more?
* Who — or which project — is overshooting the allocated budget?

CCMOs provide budgeting tools through which enterprises can apportion the cloud costs to different business units or cost centers. This could be for a team, a project, a region, or a department.

CCMO tools also provide automatic real-time budget tracking so that cost-saving actions can be taken before it is too late.

### Tagging
A tag is a label that you assign to a cloud resource. By applying tags, you add metadata to logically organize resource groups using a taxonomy.

Each tag consists of a key and an optional value, both of which the user defines. AWS and Azure call them tags, and Google Cloud calls them labels. In the Nutanix private cloud, they are called Categories.

CCMOs empower financial leaders in an organization to create cost centers and associate tags with them. CCMOs also help you associate budgets with the cost centers and then automatically aggregate all resource costs associated with tags for that particular cost center.

This helps you track your spending against allocated budgets using flexible definitions that can be changed by altering the tags associated with a cost center.

### TCO-based Cost Metering
Nutanix has created a cost model that is comprehensive, intuitive, and automated, while also being flexible and extensible to accommodate a wide range of business needs. The model incorporates defaults based on industry averages, enabling it to deliver reasonable accuracy even without site-specific configuration.

The Total Cost of Ownership (TCO) model is included in Beam and accounts for capital and operating costs in six areas, allowing you to determine the true cost of owning and operating a Nutanix private cloud solution:

* <strong>Hardware:</strong> Beam analyzes your Nutanix environment and populates the model automatically, including amortizing hardware license costs for the servers you might be using.
* <strong>Software:</strong> Software costs are amortized for all installed Nutanix software. You can optionally add costs for third-party software such as monitoring tools by adding the cost per license.
* <strong>Facilities:</strong> Power, cooling, and datacenter space costs can be difficult for IT organizations to determine directly. Beam instead estimates power and cooling costs based on your electricity consumption and the efficiency of your datacenter while using industry-standard values for cost per kWh. Datacenter space costs are calculated based on the number of nodes in use, the number of racks needed for those nodes and the per-rack cost. The model accommodates on-premises versus co-location.
* <strong>Telecom:</strong> Nutanix accounts for network switches and other telecom-related costs based on the number of nodes in your datacenter, the number of network switches needed based on the number of nodes and estimating the average cost of network switches.
* <strong>Services:</strong> The model amortizes any Nutanix or third-party professional services as part of the TCO model, including both one-time and recurring costs.
* <strong>People:</strong> The TCO model accounts for the salaries of both outsourced and internal IT administrative staff. It calculates the amount of IT admins you may need based on the number of nodes and estimates the average salary

It is important to understand that the objective is to get the users close to a reasonably good approximation of their private cloud TCO and then give them the ability to fine tune those for accuracy. Most users do not even know all these costs so getting them to a close approximation for their private cloud TCO is a very beneficial starting point.

### Cost-aware Workload Migration
A CCMO solution needs to be able to compare workload costs across public and the private clouds. By using TCO-based costing models (described above) for such a comparison you can ensure that the comparisons are accurate and account for all cost factors contributing to a workload running on any cloud.

Cost-aware workload migration involves:

* Identifying the total cost of workload in a cloud
* Comparing the cost of similarly sized workloads in other clouds
* Making recommendations on when it would result in cost savings to migrate from private cloud to public cloud

These cost comparisons need to be dynamic so that you can avoid costly sticker shock due to migrating a workload that may not be as cost effective to run in a particular cloud.

## Automated Resource Rightsizing
Your CCMO solution should also be able to automatically detect anomalous spending patterns and identify unused or idle resources. Then, to minimize manual intervention, you should also be able to create automation policies to eliminate unused resources and rightsize infrastructure to ensure optimal consumption and reduce cloud spend accordingly.

### Reserved Instance Purchases
Since reserved instances provide greater cost benefits (as we discussed earlier), your CCMO solution should be able to use your consumption history to identify the optimal reserved instance for you to purchase or exchange the reserved instances you may have already purchased from a particular type to a different type of reserved instance.

## Quiz: Cost Optimization Solutions

### QUIZ QUESTION
What is cost-aware workload migration?

* It means that the CCMO solution can identify the total cost of workload in a cloud, compare the cost of similarly sized workloads in other clouds, and make cost-aware migration recommendations

## Exercise: Beam Account Configuration

### Exercise
In this exercise you will identify how to onboard a Nutanix account in Beam to identify the true cost of workloads running on Nutanix Private Cloud.

Note: You will not use a workspace in the classroom for this exercise.

### Logging In

Beam is a SaaS service and does not require any on-premises installation.

* 1. Open a new browser tab and go to [https://beam.nutanix.com](https://beam.nutanix.com) and click <strong>Sign in with My Nutanix</strong>.
* 2. Use [hce-beam#@udacity.com](hce-beam#@udacity.com) as your email address. Replace <strong>#</strong> with your day of birth. E.g., if your birthday is January 5, that equates to [hce-beam5@udacity.com](hce-beam5@udacity.com). <strong>#</strong> will have values from <strong>1 to 31</strong>. (If for any reason your login does not work, you may try a value of <strong># = 32, 33 or 34</strong>). The password will be <strong>Nutanix1234@.</strong>

Note: Prerequisites already configured for this lab include:

* The Nutanix cluster being used for this lab is already licensed in the Nutanix Salesforce database.
* Prism Pulse is enabled for the Nutanix cluster to send VM configuration details to Beam.
* If you are not already on the <strong>Dashboard</strong> view or you are presented with the <strong>View Selector</strong>, click <strong>All Clouds</strong> in the <strong>View Selector</strong> or click the <strong>Entities</strong> menu at the upper left and select <strong>Dashboard</strong> to see the Beam default view upon login.

### Private Cloud Cost Metering

### Nutanix Account Configuration

To start using Beam, you will need to configure your Nutanix account with Beam by entering an associated license key.

### Note: For the lab environment, the license key has already been entered.

* 1. Click the <strong>Entities</strong> menu and go to <strong>Configure > Nutanix Accounts</strong>. Observe the configured license key for the <strong>Beam Lab Nutanix Account.</strong>
* 2. Logout by clicking the username HCE Beam## and selecting Log out.

## Cost Governance with Xi Beam

Financial governance involves a lot more than simply keeping costs under control. The need to centralize control across multiple teams becomes critical as enterprises foray into multi-cloud and multi-application deployments. Cloud vendors and business owners need a systematic way to map consumption to business units in complex environments.

Cloud Cost Monitoring & Optimization (CCMO) tools with governance capabilities delivered as a part of a Cloud Management Platform (CMP) can help you visualize resources by groups and departments, empowering you to manage their usage and enforce policies based on allocated budgets.

This financial governance capability creates better accountability by identifying the teams, users, or projects that are driving the cloud spending. This approach enables business owners to make data-driven spending decisions that ultimately help you get the maximum value out of your cloud investment.

### What is Xi Beam?
Xi Beam by Nutanix is a software-as-a-service product that helps customers with cost governance for both their public and private clouds. Beam’s cost optimization capabilities (called the cost optimization module) help identify cost saving opportunities in public clouds, and also enable chargeback and budgeting across public and private clouds.

Cost optimization module helps provide visibility into multi-cloud spend across clouds such as AWS, Azure, and Nutanix. It comes with several features that provide an average of 35% or more in public cloud cost savings through elimination of unused resources, right-sizing of underutilized resources and purchase or exchange recommendations for reserved instances.

![](https://video.udacity-data.com/topher/2020/September/5f6934a8_what-is-nutanix-beam/what-is-nutanix-beam.png)

### Cost Governance
At the very beginning of this lesson, we spoke briefly about cost governance. Let’s recap those points and talk about the landscape of architectures and associated costs today before we move on.

Organizations today are increasingly adopting a multi-cloud architecture that spans across private and public clouds. This provides the necessary agility and flexibility of choice needed for IT teams to quickly fulfil business needs.

However, with workloads spanning public and private clouds, there is a strong need for a cost governance solution that centralizes visibility across all clouds and implements cost governance policies to keep overall IT spending within budgets.

A key cost governance challenge in private cloud is the lack of immediate visibility into granular resource costs as opposed to public clouds, which provide an on-demand, highly granular breakdown of cost of all cloud resources based on consumption.

There are also many different cost factors to consider, beyond simply the hardware and software infrastructure licenses, when it comes to evaluating the cost of owning and running a private cloud. Lastly, in order to drive financial accountability, financial admins need the ability to chargeback spending to business units with a unified public and private cloud cost report.

![](https://video.udacity-data.com/topher/2020/September/5f6934d4_cost-governance/cost-governance.png)

### Multi-cloud Cost Management with Beam
With applications and workloads increasingly spanning private and public cloud boundaries, it is critical to ensure that businesses can track and allocate spending across clouds using multi-cloud showback and chargeback reports that span private and multiple public clouds.

In order to drive financial accountability, it is essential to have reporting mechanisms that can automatically identify and update resource costs in real-time for both public and private clouds. Beam provides a tag-based reporting structure that can be used to create highly granular cost reports and allocate spending to an appropriate business unit or cost center. However, not all resources can be or will be tagged.

In order to avoid manually going through lengthy cost reports each billing cycle to identify and allocate untagged spending to a cost center, Beam allows you to set up automated chargeback rules for untagged spending.

Set up the chargeback rule once and all future untagged resource costs will automatically get allocated to a particular cost center, saving dozens of hours of manual work each month. You can also set up budgets and track spending against those budgets so that you are proactively notified before spending goes out of control.

## Quiz: Cost Governance with Beam

### QUIZ QUESTION
What is Xi Beam?

* A software-as-a-service product that helps customers with cost governance for both their public and private clouds.

## Configuring a Cost Governance Policy in Xi Beam

Please watch the videos to follow the tutorials:

[![IMAGE ALT TEXT](https://raw.githubusercontent.com/ARBUCHELI/HYBRID-CLOUD-ENGINEER-NANODEGREE-PROGRAM-PART-2/main/images/532.jpg)](https://www.youtube.com/watch?v=9mZIq0fPYWU&feature=emb_logo)

[![IMAGE ALT TEXT](https://raw.githubusercontent.com/ARBUCHELI/HYBRID-CLOUD-ENGINEER-NANODEGREE-PROGRAM-PART-2/main/images/532.jpg)](https://www.youtube.com/watch?v=CVnyeSycap4&feature=emb_logo)

### Configuring Cloud Accounts
You can add and manage your AWS, Azure, and Nutanix accounts for cost governance using the Beam console. To configure cloud accounts, click the menu icon in the top-left corner to display the main menu. Then, click Configure and select the cloud of your choice. Beam supports three clouds at this time: Nutanix, AWS, and Azure.

### Configuring a Nutanix account for Private Cloud cost governance
You can configure your Nutanix account in Beam for cost governance. This provides private cloud metering based on a configurable TCO model, multi-cloud chargeback, and budgeting capabilities.

Beam also provides visibility into your Nutanix spend allocated granularly to Nutanix clusters and VMs, allows you to create multi-cloud cost centers and charge spending back to a budget owner.

Adding a Nutanix account is a very simple, two-step process. After logging into the Beam console, click the menu icon at the top left and select <strong>Configure > Nutanix Accounts.</strong>

![](https://video.udacity-data.com/topher/2020/September/5f693502_beam-configure-nutanix-account-1/beam-configure-nutanix-account-1.png)

Click Add Nutanix Account and, on the page that appears, enter your License Key or Serial Asset Number and click Next. Once the License Key or Serial Asset Number have been validated, Beam will fetch the account details and the cost associated with your Nutanix purchases automatically.

### Configuring an AWS account for Public Cloud Cost Governance
You can configure your AWS accounts in Beam for cost governance. This helps:

* Eliminate unused resources
* Rightsize underutilized resources
* Make intelligent reserved instance purchases or exchanges
* Facilitate multi-cloud chargeback and budgeting

Beam's cost governance capabilities allow you to control your public cloud costs and drive financial accountability.

Much like adding a Nutanix account, adding an AWS account is also simple — but involves five steps.

* 1. As before, after logging into the Beam console, click the menu at the top left and select <strong>Configure > AWS Accounts.</strong>
* 2. After clicking AWS Accounts, click <strong>Add Payer Account.</strong>
* 3. From your AWS Billing and Management console, make note of the required details for your existing AWS Cost and Usage Report (CUR). Set up billing in the AWS payer account to receive the CUR in an S3 Bucket.
* 4. Back in Beam, enter the CUR details and execute a CloudFormation template in the Payer account to assign a role to Xi Beam. Enter the report name, report prefix (if any), and S3 bucket name. Generate and execute the CFT provided by Beam in your AWS Payer account.
* 5. Finally, configure AWS linked accounts in Beam. Once you configure your AWS payer account, Beam will detect all associated linked accounts. It is recommended to generate and execute the CFT for each linked account to better optimize your cloud spend.

## Quiz: Configuring Cost Governance Policy

### QUESTION 1 OF 2
Which cloud accounts does Beam support? Select all that apply.

* Nutanix

* AWS

* Azure

### QUESTION 2 OF 2
What steps do you need to follow to add a Nutanix cloud account in Beam?

* 1. From the main menu, navigate to the configure Nutanix account page.
* 2. Enter your License Key or Serial Asset Number and click Next.
* 3. Beam will fetch the account name automatically.

## Configuring Audits and Cost Policies

[![IMAGE ALT TEXT](https://raw.githubusercontent.com/ARBUCHELI/HYBRID-CLOUD-ENGINEER-NANODEGREE-PROGRAM-PART-2/main/images/532.jpg)](https://www.youtube.com/watch?time_continue=76&v=_EBFWpaVdgw&feature=emb_logo)

An audit is a set of rules used to determine if a specific resource is unused or underutilized. Beam allows you to configure the usage parameters of an audit. A collection of these audits form a cost policy.

Beam allows you to define a specific policy for each cloud account. Beam, by default, provides you with a system policy for each cloud. You can clone the system policy to create custom policies. You can create multiple custom policies with different configurations and assign them to different cloud accounts.

To create or view a cost policy, click the menu icon at the top left of the screen and select <strong>Configure > Cost Policy</strong>. Then, in the top-right corner of the Cost Policy page, you will see two types of views available to select.

### Policy View

Lists all the policies along with other details, for example, accounts assigned, cloud type, count of accounts assigned, and so on. To create a custom policy, clone the system policy or an existing custom policy, edit the available fields according to your requirement, and assign single or multiple accounts to that policy. In this view, you can view, clone, edit, and delete a policy.

![](https://video.udacity-data.com/topher/2020/September/5f693555_beam-policy-view/beam-policy-view.png)

### Accounts View

Lists all the accounts along with other details, for example, the attached policy name, cloud type, and so on. In this view, you can click the Reassign button to assign a cost policy to a particular account. You can also select multiple accounts and click the Bulk Reassign button to assign a cost policy to those selected specific cloud accounts.

![](https://video.udacity-data.com/topher/2020/September/5f69358b_beam-accounts-view/beam-accounts-view.png)

## Quiz: Configuring Cost Policies

### QUIZ QUESTION
What is the difference between an audit and a cost policy?

* An audit is a set of rules to filter resources based on the usage parameters used to determine if a specific resource is unused or underutilized. A collection of these audits form a cost policy.


[![IMAGE ALT TEXT](https://raw.githubusercontent.com/ARBUCHELI/HYBRID-CLOUD-ENGINEER-NANODEGREE-PROGRAM-PART-2/main/images/532.jpg)](https://www.youtube.com/watch?v=cZt4I-FSL0A&feature=emb_logo)

A scope is a logical group of your cloud resources that provides you with a custom view of your cloud resources. You can define scopes using cloud, accounts, and tags. An administrator can assign read-only access to a user. This will give that user read-only access for the resources within the scope and nothing else.

To create a scope:

* 1. In the Beam console, select <strong>Beam Cost Governance</strong> from the application selection menu.
* 2. Click the menu icon in the top-left corner to display the main menu. Then, click <strong>Configure > Scopes.</strong>
* 3. Click <strong>Create a Scope</strong> to open the <strong>Scope Creation</srong> page.
* 4. On the scope creation page, name the scope; select viewers; and define the cloud, account, and tags.
* 5. Save your scope to complete the creation process.

## Quiz: Creating a Scope

### QUIZ QUESTION
What is a scope?

* A scope is a logical group of your cloud resources that provides you with a custom view of your cloud resources.

## Nutanix Cost Configuration

[![IMAGE ALT TEXT](https://raw.githubusercontent.com/ARBUCHELI/HYBRID-CLOUD-ENGINEER-NANODEGREE-PROGRAM-PART-2/main/images/532.jpg)](https://www.youtube.com/watch?v=T4639nnQIho&feature=emb_logo)

Beam provides a detailed view of the existing spend on Nutanix resources based on the purchased Nutanix products and the clusters that those products are associated with. Cost configuration for Nutanix is the key to visualize the true cost of running a Nutanix cloud.

You can configure the cost for Nutanix Products Clusters, and VMs.

To go to the Cost Configuration page, click the hamburger icon in the top-left corner to display the main menu. Then, click <strongConfigure > Nutanix Cost Configuration.</strong>

On the Nutanix Cost Configuration page, you will have access to three tabs:

### Product Portfolio

The Product Portfolio tab is a comprehensive summary of all the Nutanix products purchased to date, their capacity, and assumed market prices.

### Cluster

The Cluster tab provides a list of all the Nutanix clusters and monthly costs for each cluster. Total Cost of Ownership (TCO) model is the cost allocation basis for the clusters. You can edit the TCO details for each cluster.

### VM

The VM tab provides a list of clusters along with the VM Costing model selected for each cluster. The VM costing model allocates the amortized cost of the cluster proportionally to the VMs that are running in the cluster based on a ratio of the allocated capacity to a VM in proportion to the total capacity on the cluster that the VM is running in. The proportional allocation can be based on the actual virtual capacity or target virtual capacity which accounts for overprovisioning of virtual capacity for VMs in comparison with the available physical capacity. You can configure the allocation type at a cluster level.

## Quiz: Nutanix Cost Configuration

### QUIZ QUESTION
What are the components involved in visualizing the cost of running a Nutanix private cloud?

* VMs, Clusters, and all Nutanix Products

## AWS Cost Configuration

Beam provides you with multiple options when performing AWS cost configuration to let you choose how you want to present the cloud spend in Beam.

The options provided are:

* Cost Logic: Choose between Amortized Cost or Absolute Cost.
* Billing: Choose between blended cost and unblended cost.
* Credits and Refunds: Choose to include or exclude the credits and refunds in the cost report.
* AWS EDP: Choose to include or exclude the Enterprise Discount Program (EDP) discount in the cost report.

All cost information that Beam presents is based on the options that you select.

### Cost Logic
Cost Logic determines how AWS RI, Savings Plan, EDP, Credits, Refunds, and Taxes are reported in Beam.

### Amortized Cost Logic
Cost reporting is based on accrual-based accounting. For Reserved Instances (RI) and savings plan, the cost reporting is based on the effective cost column in the AWS CUR. For EDP, Credits and Refunds, and Taxes, Xi Beam does the amortization calculation.

In the case of taxes, AWS reports the amortized cost of the tax at the account level. Xi Beam does the amortization calculation at the service, region, resource level, and so on.

Amortized Cost logic is useful when you want to view the cost of resources on an accrual basis considering the usage of RI, Savings Plan, Discounts, and Taxes specific to that resource.

### Absolute Cost Logic
Cost reporting is based on cash-based accounting. The RIs, savings plan, EDP, Credit and Refunds, and Taxes are not amortized over the billing period.

If you select the Absolute Cost option as the cost logic, the cost of RI, Savings Plan, EDP, Credits and Refunds is shown as a separate line item, and cloud resource cost is reported without the apportioned cost of RI, Savings Plan, and so on. This results in a spike on the day monthly RI fee or upfront RI fee gets charged.

### Billing
You can select between blended cost and unblended cost.

### Unblended Cost
If you select the Unblended Cost option, Beam reports the cost of resources based on usage. Selecting this option reports the cost of resources from the Unblended Cost column in the AWS CUR.

### Blended Cost
If you select the Blended Cost option, Beam reports the cost of resources based on the average cost of usage across the consolidated billing family. Selecting this option reports the cost of resources from the Blended Cost column of the AWS CUR.

### Credits and Refunds
Beam provides you with the option to include or exclude credits and refunds in the cost report irrespective of the Amortized Cost or Absolute Cost selection.

If you select the Include option, Credits and Refunds are shown in the cost report as a separate line item or amortized and apportioned to a resource depending on the selection between the absolute cost or amortized cost, respectively.

If you select the Exclude option, Credits and Refunds are not shown in the cost report to the user (for example, Scope or Cost Center viewers). It also gets excluded from the Analyze page.

### AWS Enterprise Discount Program (EDP)
AWS provides enterprises with a discount on its services against a volume spend commitment. For example, an enterprise commits to spending $2 million on AWS services and receives a certain percentage of the discount. The enterprise must pay $2 million even if they do not spend the amount.

Beam provides you with the option to include or exclude the EDP discount in the cost report. EDP discount is applicable to both amortized and absolute cost logic.

If you select the Include option, EDP discount is shown in the cost report as a separate line item or amortized and apportioned to a resource depending on the selection between the absolute cost or amortized cost, respectively. If you select the Exclude option, EDP discount is not shown in the cost report to the user (for example, Scope or Cost Center viewers). It also gets excluded from the Cost Analyze view.

You can add EDP contract details in Beam. Adding the EDP contract details allows you to view the projected spend after the EDP discount is accounted for in the Cost Analyze view. Any discount from EDP applied to the current usage gets reported in CUR and Beam reports accordingly.

For future projections, you need to add contract details which Beam will use accordingly.

## Quiz: AWS Cost Configuration

![](https://raw.githubusercontent.com/ARBUCHELI/HYBRID-CLOUD-ENGINEER-NANODEGREE-PROGRAM-PART-2/main/images/533.jpg)

## Implementing Public Cloud Cost Savings in Beam

Beam’s cost optimization module helps identify cost saving opportunities in public clouds and also provides financial governance across public and Nutanix private cloud.

In this section, we will discuss how to identify potential cost savings for AWS and walk through various Beam cost saving suggestions. The same capabilities also apply to Azure. We’re going to discuss:

* Viewing cloud cost details
>> * We’ll cover several of Beam’s cost overview and analysis capabilities, as well as the dashboards and screens that are associated with them.

* Eliminating unused resources
>> * We will explore how you can use the Save dashboard to remove unused resources or ignore them in future audits with just a few clicks.

* Rightsizing resources based on usage patterns
>> * In this topic, we will look at how to optimize resource allocation — such as CPU and memory — for underutilized resources.

* Purchasing reserved instances
>> * And finally, we’ll also discuss how you can leverage Beam’s purchase recommendations for reserved instances to incur even greater cost savings.

## Viewing Cloud Cost Details

[![IMAGE ALT TEXT](https://raw.githubusercontent.com/ARBUCHELI/HYBRID-CLOUD-ENGINEER-NANODEGREE-PROGRAM-PART-2/main/images/532.jpg)](https://www.youtube.com/watch?v=izu8jnCDYpQ&feature=emb_logo)

The first thing you need to do is select your AWS Account. In the sample selection here, as you can see, the AWS account has multiple payer accounts associated with it.

![](https://video.udacity-data.com/topher/2020/September/5f69381b_aws-account-selection-blurred/aws-account-selection-blurred.png)

After you select an account, the dashboard will update to display information specific to your AWS account. You will typically see five widgets:

* Spend Overview
* Spend Analysis
* Spend Efficiency
* Spend Anomalies
* Reserved Instances

![](https://video.udacity-data.com/topher/2020/September/5f693839_aws-summary-dashboard-combined/aws-summary-dashboard-combined.png)

This is your overall cost view for a given account. When you want a summary of everything that’s going on with a cloud account, and to quickly check important statistics or identify anomalies, this is the page you will come to.

Then, to see more granular information about current and projected spend, click the menu icon at the top left and click Analyze. On the Analyze screen, you will see an overview of your current spend by default, with options to view current spend by account, service, region, API operation, purchase option, and tags. The Tags option also provides a filter that allows you to select specific tags and filter the data accordingly.

![](https://video.udacity-data.com/topher/2020/September/5f693859_analyze-current-spend-2/analyze-current-spend-2.png)

You can also view projected spend using historical data from up to 9 months prior, as well as the costs associated with compute, storage, databases, and data transfer out of the public cloud.

## Quiz: Viewing Cloud Cost Details

### QUIZ QUESTION
You have an Azure account that’s linked to Beam and want to view details about the projected spend for the next 3 months. How will you navigate to the page that provides information?

* Menu > Analyze > Projected Spend

## Eliminating Unused Resources

[![IMAGE ALT TEXT](https://raw.githubusercontent.com/ARBUCHELI/HYBRID-CLOUD-ENGINEER-NANODEGREE-PROGRAM-PART-2/main/images/532.jpg)](https://www.youtube.com/watch?v=pamNfGXXSZ0&feature=emb_logo)

To eliminate unused resources, click the menu icon at the top left of the screen and select Save. By default, you will be taken to the Save Dashboard, which displays two broad categories of information: Projected Savings and Optimization Opportunities.

![](https://video.udacity-data.com/topher/2020/September/5f69415f_save-overview/save-overview.png)

The Projected Savings section:

* Indicates whether or not there is room in your current cloud spend for optimization based on Beam’s analysis
* Provides an overview of your spend efficiency, potential savings, quarterly costs, and the money and time you’ve saved till date by acting upon Beam’s savings recommendations

Optimization Opportunities, on the other hand, consists of three distinct sections – unused cloud resources which you can eliminate to incur savings; rightsizing actions that you can take to optimize spending on instances; and a history of your savings.

To eliminate unused resources, in the Optimization Opportunities section, click the <strong>Eliminate</strong> link. You will be navigated to this page, which provides more details about unused resources you can remove, the potential cost savings from each, as well as the total savings that you will incur.

![](https://video.udacity-data.com/topher/2020/September/5f694179_save-eliminate-unused-resources/save-eliminate-unused-resources.png)

As you can see here, there are a number of old snapshots, as well as unused IPs, ELBs, volumes, hosted zones, and so on. To take action here, first we need to click <strong>View List.</strong> That will take us to a page with even more details about the unused resource in question.

![](https://video.udacity-data.com/topher/2020/September/5f694198_save-snapshot-details/save-snapshot-details.png)

Taking the unused snapshots as an example, on the details page, we have several options that we can use. We can:

* Suppress some or all of the snapshots because you may not want to eliminate them
* Eliminate some or all of the snapshots so that you can benefit from cost savings
* Raise a ServiceNow ticket for IT assistance with finding the appropriate person to act on the cost saving recommendation

Suppressing some or all of the snapshots simply means that Beam will no longer include them in future audits. To suppress a snapshot, select it from the list and then click <strong>Actions > Suppress Selected.</strong> You will be presented with a confirmation dialog box, in which you will need to provide a reason for your choice and then click Suppress.

![](https://video.udacity-data.com/topher/2020/September/5f6941b4_save-suppress/save-suppress.png)

To eliminate a snapshot, select it and click <strong>Actions > Eliminate Selected.</strong> Once again, you will be prompted for confirmation. Simply select the checkbox and then click <strong>Yes, Eliminate.</strong>

![](https://video.udacity-data.com/topher/2020/September/5f6941d1_save-eliminate/save-eliminate.png)

On the other hand, if you believe Beam’s cost audit needs to be changed to meet your organization’s requirements, you can edit the cost policy that governs this. Click the <strong>Edit Cost Policy</strong> link to view the cost policy responsible for flagging unused snapshots and modify it as needed.

### QUESTION 1 OF 2
What is the difference between suppressing an unused resource and eliminating it?

* Suppress prevents a resource from being audited in the future; eliminate deletes the resource

![](https://raw.githubusercontent.com/ARBUCHELI/HYBRID-CLOUD-ENGINEER-NANODEGREE-PROGRAM-PART-2/main/images/534.jpg)

## Rightsizing Underutilized Resources

[![IMAGE ALT TEXT](https://raw.githubusercontent.com/ARBUCHELI/HYBRID-CLOUD-ENGINEER-NANODEGREE-PROGRAM-PART-2/main/images/532.jpg)](https://www.youtube.com/watch?v=KQgeoL5uv5I&feature=emb_logo)

Another option available to you for cost savings is rightsizing underutilized resources. There are two ways you can access the Optimization section. From the row of options at the top of the screen, select <strong>Optimize.</strong>

![](https://video.udacity-data.com/topher/2020/September/5f6943ed_save-access-rightsize-2/save-access-rightsize-2.png)

Alternatively, on the Save Overview page, from the Optimization Opportunities widget at the bottom of the page, in the Cloud Rightsizing section, click <strong>Optimize.</strong>

![](https://video.udacity-data.com/topher/2020/September/5f694405_save-access-rightsize-1/save-access-rightsize-1.png)

As with the ability to eliminate unused resources, choosing to optimize will take you to a page with a list of all potential resources for optimization. These include EBS volumes, EC2 instances, RDS PIOPS, EBS PIOPS, and more.

![](https://video.udacity-data.com/topher/2020/September/5f69441a_save-optimize-cloud-resources/save-optimize-cloud-resources.png)

As an example, let’s take a closer look at rightsizing underutilized EC2 instances. As before, click View List to see more details about the EC2 instances and actions you can take. In this case, you will see a list of instances with low CPU and memory utilization. For each line item that is displayed, you can click the arrow at the far right to view additional details about the instance itself, as well as a chart showing utilization data over time.

![](https://video.udacity-data.com/topher/2020/September/5f694431_save-optimize-line-item-details/save-optimize-line-item-details.png)

As you can see, in addition to providing details, Beam also provides a sizing recommendation. In the image above, the instance is a t2.micro and, based on utilization, Beam has concluded that it would be better as a t2.nano instance. This will reduce the cost from $9.94 to $4.97 which is nearly a 50% reduction in spending on this EC2 instance. Once you have this information, you can then plan your optimization effort.

While Beam cannot automatically optimize the instance size for you, it does provide step-by-step instructions so that you can do so yourself. Click the <strong>How to optimize?</strong> link to view a popup with details. If you want to optimize the other instances as well, use the arrows at the top left of the popup to view details and optimization instructions for each instance.

![](https://video.udacity-data.com/topher/2020/September/5f69444b_save-optimize-popup/save-optimize-popup.png)

## Quiz: Rightsizing Underutilized Resources

### QUIZ QUESTION
During a routine audit of your clouds on Beam, you have discovered a number of EC2 instances running important applications that could do with optimization. According to Beam’s analysis, the EC2 instances have been assigned more resources than they actually need, so there’s an opportunity for cost savings here. What should you do about this?

* Rightsize the EC2 instances so that you are paying for only the required amount of resources

## Reserved Instance Purchases and Exchanges

[![IMAGE ALT TEXT](https://raw.githubusercontent.com/ARBUCHELI/HYBRID-CLOUD-ENGINEER-NANODEGREE-PROGRAM-PART-2/main/images/532.jpg)](https://www.youtube.com/watch?v=zpegBiiX1rk&feature=emb_logo)

The third way in which Beam provides cost savings is by making purchase or exchange recommendations for reserved instances. And before we move forward with what this looks like in Beam, let’s take a moment to understand the idea behind the feature.

Reserved Instance recommendations are made for compute or database instances of a particular instance family. AWS and Azure have many instance families to give customers the ability to choose what works for them.

So, AWS has m5d as an instance family type, with sizes such as m5d.small, m5d.medium, m5d.large, and so on. Another instance family type is z1d with instance sizes such as z1d.small, z1d.medium, z1d.large, and so on.

The first part of what Beam does in this context - that is, for reserved instance purchases - is recommending which instance type you should buy based on a historical analysis of your usage.

So, to take this example forward, let’s say you decide to purchase a reserved instance based on Beam’s recommendation. When you purchase reserved instances from AWS you have to specify the instance type. In this case, let’s say you purchased the m5d.

It’s important to note here that the reservation you purchase will only apply to that particular instance family unless you have specifically asked for a convertible type of reserved instances, which are more expensive than non-convertible.

Convertible instances can switch between EC2 instance family types. So, although you’ve purchased an m5d instance, perhaps your needs change over time. Perhaps you are no longer running m5d instances 24x7 and your reservation-based pricing is no longer being used. And instead of m5d, you are constantly running z1d type instances. If your reservation was of a convertible type then you will be able to switch it from RI for m5d to RI for z1d.

This is the second half of this feature - reserved instance recommendations. Beam performs this analysis automatically for you and will tell you when you have convertible instances that are no longer being optimally used for a particular family type but could be converted to a different family type.

### The Purchase Dashboard
Now, let’s look at the feature itself. Unlike the two cost saving features we discussed in the previous sections, this particular feature is accessed from the Purchase section of Beam. To get there, click the menu icon at the top left of the screen and select Purchase. You will see the Purchase dashboard.

![](https://video.udacity-data.com/topher/2020/September/5f694474_purchase-overview/purchase-overview.png)

Here, you will see four sets of information:

* Reserved Instance (RI) coverage
* RI status
* RI calculator
* Top recommendations

The Top Recommendations section is what we’re currently interested in. Beam provides the recommendations listed here using a historical analysis of your usage. You can define the lookback period yourself in order to ensure that Beam’s recommendations are tailored to your specific needs. The default lookback period is 14 days by default but can be extended to 30 days. For more details, either click View All Recommendations at the bottom of the screen, or click Buy from the row of options at the top.

Beam makes these recommendations by analyzing all the instances (compute or database) that are running 24x7 over the lookback period. A list of such instances is provided towards the bottom of the page. For compute instances, these could be of many different sizes (small, medium, large, etc.).

![](https://video.udacity-data.com/topher/2020/September/5f694492_purchase-buy-ri/purchase-buy-ri.png)

The purchase recommendations table provides a list of reserved instances (compute or database) that would be ideal to purchase based on existing consumption patterns; the size, platform, location, type, and quantity of those instances; as well as a comparison of the on-demand and reserved cost, and the savings you will incur as a result. Clicking the arrow at the far right of any of the line items in the table will take you to a page with more details about the recommendation.

Several key details are available on this page, to help you make an informed decision about whether or not to invest in an RI. For example, there are high upfront costs associated with an RI purchase but in the long run purchasing an RI leads to significant cost savings for the compute or database instances that will be heavily used. Beam performs a breakeven analysis to ease the decision-making process making it simple for you to decide - am I going to run this particular instance 24x7 for a certain number of months? If so, I should switch to a reservation based plan instead of paying on-demand pricing.

Beam makes these recommendations by analyzing all the instances (comput4 or database) that are running 24x7 over the lookback period. A list of such instances is provided towards the bottom of the page. For compute instances, these could be of many different sizes (small, medium, large, etc.).

![](https://video.udacity-data.com/topher/2020/September/5f6944ac_purchase-breakeven-analysis/purchase-breakeven-analysis.png)

## Quiz: Reserved Instance Purchases

### QUIZ QUESTION
What information does Beam present about reserved instances in the Top Recommendations section?

* Suggestions for which reserved instances to purchase based on historical analysis of your usage

## Implementing Cost Governance for Private Cloud

In addition to finding potential public cloud cost savings, Beam’s cost optimization module also helps to create multi-cloud chargeback reports that drive accountability in terms of who is consuming what cloud resources.

You can use tags to create highly customizable cost center views, allocate them to business units, send out cloud consumption reports and set up budget alerts. When consumption nears an allocated budget, Beam will send budget alerts so that you can take proactive cost saving actions to prevent your budget from being exceeded.

In this section, we will discuss:

* Nutanix TCO Configuration: Beam provides a total cost of ownership (TCO) model for Nutanix, which provides an accurate picture of the cost of owning and operating your on-prem infrastructure.

* Cluster and VM Costing: Shows the cost view for different clusters that Beam manages, as well as the cost of each individual VM running on a given cluster.

## Nutanix TCO Configuration

[![IMAGE ALT TEXT](https://raw.githubusercontent.com/ARBUCHELI/HYBRID-CLOUD-ENGINEER-NANODEGREE-PROGRAM-PART-2/main/images/532.jpg)](https://www.youtube.com/watch?v=IBk6KY2U5V4&feature=emb_logo)

Beam provides a total cost of ownership (TCO) model for Nutanix that shows the total cost of owning your Nutanix private cloud. It includes more than just the hardware and software license costs and provides an accurate picture of owning and operating your on-prem infrastructure.

The benefit that this TCO model provides is immediate, out-of-the-box visibility into an approximation of the total on-prem costs. It’s incredibly useful to get a reasonably close approximation without asking a customer to input anything other than a license key number. In order to do this, the TCO model makes many assumptions and uses certain pre-configured industry standard values (eg: an average cost of $0.1 per kWh) which will vary from customer to customer but not by a whole lot. Customers get the benefit of a close enough approximation due to these pre-configured industry standard values and then, if they want, they can fine tune the values for more accuracy.

As with AWS, in order to get started, we need to select our Nutanix account first. Once that has been done, you will see Beam’s main dashboard update accordingly.

![](https://video.udacity-data.com/topher/2020/September/5f694561_beam-labs-analyze-dashboard-single-cluster-details-page/beam-labs-analyze-dashboard-single-cluster-details-page.png)

The dashboard provides four pieces of information:

* An overview of your spend based on clusters
* Spend analysis, and you can use a filter to view either daily or monthly details
* Capacity analysis, with a similar filter for daily and monthly details
* Recommended purchases

Once you’re familiar with the dashboard, the next step is to ensure that Beam has been set up to use the Total Cost of Ownership model for Nutanix infrastructure cost calculations and modeling.

To determine this, click the menu icon at the top left corner and select <strong>Configure > Nutanix Cost Configuration.</strong> Then, on the Cost Configuration page, click the Cluster tab. Since TCO is the default cost allocation basis, it will be displayed at the top of the page.

![](https://video.udacity-data.com/topher/2020/September/5f69457a_beam-labs-tco-cost-cluster-tab/beam-labs-tco-cost-cluster-tab.png)

If you want to drill down and view additional details for any of the clusters listed here, click the Edit TCO link at the rightmost corner of any line item. The page that is displayed lists all of the major cost heads that comprise the TCO model.

They are:

### Hardware: 
Includes Nutanix hardware license cost, which is automatically pulled from the sales database. Custom third-party hardware costs can be easily added here as well.

### Software:
Includes Nutanix software license cost, which is automatically pulled from the sales database. The cost of any nodes running vSphere are also automatically added using configurable pricing. Custom third-party software costs can be easily added.

### Facilities:
Includes power and cooling costs, and datacenter space costs for an on-prem hosted or a co-located datacenter. The power and cooling costs assume a certain efficiency ratio, power consumption (in kW) per hour for each node and cost per kWh. Datacenter space costs assume a certain cost per datacenter rack and the number of nodes that fit in a rack.The model calculates total power & cooling costs based on the number of Nutanix nodes and multiplying that by the cost of power consumed per node. The model calculates total datacenter space costs based on the number of Nutanix nodes and multiplying that by the cost of the datacenter racks needed per node.

### Telecom:
Includes Ethernet/top of rack switch costs. The model assumes a certain number of ethernet ports needed per node, the number of ports in an ethernet switch and the cost per ethernet switch. The model calculates total Telecom costs based on the number of Nutanix nodes and multiplying that by the cost of ethernet switches needed per node.

### People: 
IT admin salary based on the number of admins you need to manage your Nutanix infrastructure and an assumed salary for them.

### Services:
Any Nutanix or third-party professional services that you may have paid for.

![](https://video.udacity-data.com/topher/2020/September/5f694598_beam-labs-tco-cost-facilities-page/beam-labs-tco-cost-facilities-page.png)

The TCO model is highly customizable and can be set for each cluster. Beam uses Pulse to track the VMs running in each cluster and allocate the cluster level cost (calculated using the TCO model) to each individual VM. The cost calculation depends on the resources allocated to that VM relative to the total resources on that cluster and how long the VM was running.

Now, if we return to the Cost Configuration page and turn our attention to the second tab, VM, you’ll notice something interesting.

When you switch to the VM tab, you will see an option to specify Actual Virtual Capacity or Target Virtual Capacity. This applies to all VMs in the cluster for which this option is selected.

What does actual virtual capacity mean? Beam gets information about the virtual capacity allocated to each VM, such as vCPUs, and virtual storage. (If you think back to the earliest lesson of this program, this is possible because the physical compute and storage capacity on a cluster are virtualized before they are allocated to VMs.) These vCPUs and virtual storage resources are actually assigned to the VM - hence the name "actual virtual capacity".

But what about scenarios in which users don’t like the virtual capacity that Beam allocates? If users want to select their own capacity, they can switch to Target Virtual Capacity and specify the ratio in which they want their physical resources to be virtualized and allocated to their VMs. That is, they can specify the vCPU:pCPU ratio (pCPU = physical CPU) and similarly vStorage:pStorage ratio. This is known as an overcommit ratio.

![](https://video.udacity-data.com/topher/2020/September/5f6945b1_beam-labs-tco-cost-vm-tab/beam-labs-tco-cost-vm-tab.png)

## Quiz: Nutanix TCO Configuration

![](https://raw.githubusercontent.com/ARBUCHELI/HYBRID-CLOUD-ENGINEER-NANODEGREE-PROGRAM-PART-2/main/images/535.jpg)

## Cluster and VM Costing

[![IMAGE ALT TEXT](https://raw.githubusercontent.com/ARBUCHELI/HYBRID-CLOUD-ENGINEER-NANODEGREE-PROGRAM-PART-2/main/images/532.jpg)](https://www.youtube.com/watch?v=Jd1bvN8PQjY&feature=emb_logo)

To view a summary of your VM and Nutanix cluster costs, click the menu button at the top left of the screen and select <strog>Analyze.</strong> From the row of options at the top left, select <strong>VM Costing.</strong>

![](https://video.udacity-data.com/topher/2020/September/5f6945d9_beam-labs-analyze-page-vm-costing/beam-labs-analyze-page-vm-costing.png)

The costs that you see in the Spend Overview widget represent the real cost of running Nutanix clusters — assuming that the TCO model has been configured correctly. To drill down further, choose a cluster from the Cluster Details widget at the bottom of the screen and click <strong>View Details.</strong>

At first glance, the details page seems similar to the VM Costing dashboard — but a closer look will reveal noticeable differences.

![](https://video.udacity-data.com/topher/2020/September/5f6945f2_beam-labs-analyze-dashboard-single-cluster-details-page-1/beam-labs-analyze-dashboard-single-cluster-details-page-1.png)

The Total Cost of Ownership widget is specific to the selected cluster, but contains the same breakdown with Cost Heads as the overview dashboard. The cluster details widget provides a lot of useful information about the cluster itself, including the hypervisor, number of VMs, the status of Pulse, and the ratio of physical to virtual CPUs and physical to virtual storage.

Finally, the table at the bottom provides a list of all VMs running on that cluster, along with their name; VM ID; details about vCPUs, memory, storage, state, and active hours; as well as the total cost involved in running that VM and the cost per hour.

## Quiz: Cluster and VM Costing

### QUIZ QUESTION
What are the cost heads that factor into the TCO calculation for Nutanix private cloud infrastructure?

* Services, Facilities, Hardware, People, Telecom, Software

## Exercise: Product Costs

In this exercise, you will ensure Beam has accurate cost data for the private cloud.

Again, you won’t need a workspace for the exercise, you’ll work in a new browser tab.

* 1. In a new web browser tab, go to [https://beam.nutanix.com](https://beam.nutanix.com) and click <strong>Sign in with My Nutanix.</strong>

* 2. Use **hce-beam##@udacity.com as your email address. Replace ## with your day of birth. E.g., if your birthday is January 5,that equates to [hce-beam05@udacity.com]. ## will have values from 01 to 31. (If for any reason your login does not work, you may try a value of ## = 32, 33 or 34). The password will be Nutanix1234@**.

* 3. From the toolbar at the top left, click the <storng>Entities</strong> menu and select <strong>Configure > Nutanix Cost Configuration.</strong>

### NOTE: Once a license key has been entered, Beam will populate your company's entire purchase history. Beam automatically populates product costs based on assumed market prices for all Nutanix products. The data shown in this lab is an anonymized example of the data populated for a company.

* 4. If you are presented with a <strong>Disclaimer</strong> notice, click <strong>I Accept and Continue</strong>. Click the blue <strong>Configure Cost</strong> button to view how a customer can customize their exact costs for each purchase. This allows users to fine tune the cost of their Nutanix software and hardware licenses in case it is different from the market price that is assumed by Beam.

* 5. The <strong>Inline cost editing</strong> box is selected by default and allows you to modify the <strong>Term</strong> (in months) and Cost. Review the Nutanix products and configurable columns. For bulk updates, click in the <strong>Upload and import</strong> box. An Excel spreadsheet of the <strong>Nutanix Cost Configuration Guidelines</strong> and the collected data from Nutanix can be downloaded, modified and uploaded.

* 6. Click the <strong>X</strong> at the upper right to close Cost Configurations.

### TCO Configuration

Beam uses a built-in total cost of ownership (TCO) model for Nutanix that provides out-of-the-box visibility into the true cost of running the Nutanix private cloud.

The TCO model includes several cost heads that are automatically populated depending on the number of Nutanix nodes and some industry standard assumptions that are built into the model. Learn how to configure the TCO model:

* 1. Go to <strong>Entities > Configure > Nutanix Cost Configuration.</strong> Above the blue <strong>Configure Cost</strong> button, select the <strong>Cluster</strong> tab.

* 2. You are presented with a list of pre-configured/pre-discovered clusters. Select a cluster and take note of the last four digits in the <strong>Cluster ID</strong> and save this ID in Notepad/Wordpad and place in your <strong>Workspace</strong> folder. <strong>You will need this in a later exercises.</strong> Click <strong>Edit TCO</strong> next to that cluster.

* 3. On the cluster page, the Hardware tab is selected by default. Click on <strong>Nutanix Hardware Cost.</strong> This reflects the cost of the NX-series hardware servers that power your private cloud. This cost is automatically pulled by Beam based on the customer purchase history. Various fields such as the product model, number of blocks and number of nodes are automatically populated based on purchase history. The total hardware purchase cost is amortized to show a monthly value based on the number of months in the purchase term.

* 4. You can also see third party hardware costs by clicking <strong>Third Party Hardware Costs</strong> and reviewing the current values. These costs reflect the underlying hardware servers that Nutanix supports as OEM or third-party nodes different from the NX-series hardware servers. By clicking <strong>Configure</strong> you can modify the OEM/third party hardware costs if they are different from those calculated by Beam.

* 5. Customers can also optionally enter a custom value for their memory costs by clicking on Edit Custom RAM cost. Beam knows how much RAM is available for a particular Cluster (shown under Memory Capacity in GB) but does not have the cost of memory purchase. Customers can manually enter a monthly memory cost per GB and Beam will add the total monthly cost for memory to the TCO model.

* 6. Add a third party custom software cost. Click the <strong>Software</strong> tab and then click <strong>+ Add Custom Third Party Software Cost.</strong> Fill out the fields in the following order:

Cost Description: ABC Software Licensing Cost per License: 50 Cost Type: Term Based Term: 5 years Start Date: Choose the current month and year. Recurring: Monthly Number of Licenses: 25000

* 7. Click <strong>Add Costs.</strong> This should now show <strong>Third Party Software Cost</strong>with a current value of $20,833. Click the dropdown arrow next to the dollar amount to see the custom configuration details.

* 8. Add a third party custom service cost. Click the <strong>Services</strong> tab and them click <strong>+ Add Custom Third Party Services Cost.</strong> Fill out the fields in the following order:

Cost Description: Onsite Consultant Start Date: Choose the current month and year. Cost Type: Recurring Cost to be Added: 10000 End Date: Choose December of next year. Recurring: Monthly

* 9. Click <strong>Add Costs.</strong> This should now show <strong>Custom Services Cost</strong> with a current value of $10,000. Click the dropdown arrow next to the dollar amount to see the custom configuration details.

* 10- Navigate through the other tabs to familiarize yourself with the information presented. All costs are amortized to a monthly level.

### Software

Includes all Nutanix software license costs which are automatically pulled from customer purchase history in Salesforce. Costs associated with any Nutanix nodes running vSphere are also automatically calculated assuming a vSphere license cost of $210/processor and 2 processors per node.

Any additional software costs, such as a third-party application performance monitoring software cost can be added manually. All software costs are amortized on a monthly basis.

### Facilities

Includes power and cooling costs, and datacenter space costs for the datacenter used to run the Nutanix Private Cloud.

### Telecom

Includes Ethernet/top-of-rack switch costs that are automatically calculated depending only on number of nodes.

### Services

This cost head includes any Nutanix or third-party professional services that you may have paid for.

### People

This cost head includes the cost incurred on IT Admin salaries for the administrative staff employed to maintain your Nutanix Private Cloud.

The power of the TCO model lies in being able to centralize all costs associated with a private cloud into one unified view and providing a good approximation of the customer private clouds cost without any configuration needed at all. At the same time, the TCO model is highly customizable and can also be configured separately for each cluster.

* 1. Close the TCO view by clicking the <strong>X</strong> at the upper right.

* 2. Above the blue <strong>Configure Cost</strong> button, click the <strong>VM</strong> tab and review the configuration for VM costs. In the <strong>VM Costing Model</strong> column, you can toggle between the <strong>Actual Virtual Capacity</strong> or a specified <strong>Target Virtual Capacity</strong> for the <strog>VM Costing Model.</strong>

### Cluster and VM Costing

The next step is to allocate the cluster level costs to individual VMs running on the cluster.

* 1. Click the <strong>Entities</strong> menu and select <strong>Analyze.</strong> A user experience popup may show offering a tour of the product. You may take the tour or close the popup.

* 2. On the <strong>Analyze</strong> page, look to the upper right, next to <strong>View:.</strong> This is the <strong>View Selector.</strong> Make sure it says <strong>Nutanix.</strong> If this shows <strong>AWS</strong> or <strong>Azure</strong>, then click on it to popup the <strong>View Selector.</strong>

* 3. In the <strong>View Selector</strong> dialog box, click <strong>Nutanix</strong> in the left column and then click the <strong>Beam Lab Nutanix Account</strong> under <strong>Select Account.</strong> This will change the view to show the Nutanix account information.

* 4. Click the <strong>VM Costing</strong> tab and under <strong>Cluster Details,</strong> search for the last four digits of the <strong>Cluster ID</strong> you saved earlier in your <strong>Workspace</strong> folder.

* 5. Click <strong>View Details</strong> to see the detailed TCO based cost breakdown for this cluster.

* 6. In this view you will see detailed cost analysis for each VM. Click on any row to see the VM cost analysis over a period relative to the resources allocated to the VM (vCPU, Storage, Memory)

### Note: The cost of each individual VM running in this cluster has been automatically calculated. If the TCO model has been accurately configured, these costs represent the true cost of running that VM in the Nutanix Private Cloud. This is critical information that should be available to modern Hybrid Cloud Engineers so that they can more accurately make decisions on which cloud is suitable for which workload, at least from a cost perspective.

### Note: It takes up to 6 hours for VM costing data to show up after a Nutanix account is configured in Beam. The TCO model is baked into the product and VM costs will be calculated out-of-the-box using the default values of the TCO model. The model can be fine-tuned depending on customer need.

* 7. Logout by clicking the username <strong>HCE Beam##</strong> and selecting <strong>Log out.</strong>

## Exercise Solution: Product Costs

[![IMAGE ALT TEXT](https://raw.githubusercontent.com/ARBUCHELI/HYBRID-CLOUD-ENGINEER-NANODEGREE-PROGRAM-PART-2/main/images/536.jpg)](https://www.youtube.com/watch?v=62aS7ci2MzM&feature=emb_logo)

## Driving Financial Accountability Through Chargeback

The Chargeback feature enables the financial control of your cloud spend by providing the ability to allocate costs associated with cloud resources to the appropriate departments that may have consumed those resources. This is done using an automated tag-based definition process. It provides a single, consolidated view of your finances across all your cloud accounts - private or multiple public clouds.

In this section, we’re going to cover two major capabilities:

* Cost Centers and Business Units: A cost center is a collection of resources within a single or multiple cloud accounts. You can assign the resources to the cost center based on cloud accounts and tags. You can either allocate a complete account or resources within an account to a cost center. A business unit is defined as a collection of cost centers. For example: you may have an Engineering business unit with multiple cost centers corresponding to the multiple engineering projects that might be the responsibility of that business unit.

* Budgets and Budget Alerts: Although we’ll discuss this in more detail later, right now it’s important to note that budgets are highly customizable and can be defined for resource groups that span cloud accounts, regions, services or tags. You can set daily, weekly, or monthly budget limit alerts to track your cloud budget. If the threshold for cloud expenses is exceeded, Beam sends an email alert. You can specify who receives the email alert, and these alerts can be sent to multiple people.

## Cost Centers and Business Units

[![IMAGE ALT TEXT](https://raw.githubusercontent.com/ARBUCHELI/HYBRID-CLOUD-ENGINEER-NANODEGREE-PROGRAM-PART-2/main/images/532.jpg)](https://www.youtube.com/watch?v=LQa41XtEOmg&feature=emb_logo)

A cost center is a collection of resources within a single or multiple cloud accounts. You can assign resources to a cost center based on tags. You can either allocate a complete account or resources within an account to a cost center.

A business unit is defined as a collection of cost centers. You can use the business units to define hierarchies in your organization between different departments. It is not necessary to define a business unit to create chargeback views. You can define chargeback based only on cost centers.

To access the Chargeback section of Beam and work with cost centers and business units, click the menu icon at the top left of the screen and select Chargeback. The dashboard that appears summarizes spending by cost center and business unit.

![](https://video.udacity-data.com/topher/2020/September/5f694624_chargeback-allocated/chargeback-allocated.png)

On the Chargeback dashboard, you can switch between viewing Allocated and Unallocated resources, view data from different periods of time using a drop down menu, and create a business unit or a cost center.

Creating a cost center, as you may expect by now, simply involves filling out a form. You need to provide a name for the cost center, specify the owners, and optionally add viewers and the business unit with which this cost center is meant to be associated.

Then, you need to define the cost center, which involves adding one or more cloud accounts, sub-accounts, and tags to that cost center. After your cost center has been defined, you need to save the definition and then save the cost center to complete the process.

![](https://video.udacity-data.com/topher/2020/September/5f69463e_chargeback-create-cost-center/chargeback-create-cost-center.png)

![](https://video.udacity-data.com/topher/2020/September/5f694658_beam-labs-define-cost-center-dialog-box/beam-labs-define-cost-center-dialog-box.png)

Since a business unit is a collection of cost centers, creating one is even simpler. You simply need to specify a name, the owners, viewers, and associated cost centers to create a business unit. No other information is needed.

![](https://video.udacity-data.com/topher/2020/September/5f694675_chargeback-business-unit/chargeback-business-unit.png)

To actually charge the cost of unallocated resources back to a business unit, on the Chargeback page, switch to the Unallocated tab. The dashboard will display an overview of spending, an analysis of the unallocated cost, a list of the highest contributors to cloud spend, and a detailed list of unallocated items.

If you’re wondering why the items in this list are unallocated, it’s because they were either not tagged at all or their tags were not covered under the cost center definition.

To allocate the cost to a cost center, first select an item from the list in the bottom half of the page, and then click <strong>View Details.</strong>

![](https://video.udacity-data.com/topher/2020/September/5f69468e_beam-labs-chargeback-1-unallocated-tab/beam-labs-chargeback-1-unallocated-tab.png)

![](https://video.udacity-data.com/topher/2020/September/5f6946a5_beam-labs-chargeback-2-click-view-details/beam-labs-chargeback-2-click-view-details.png)

When you click View Details, you will be taken to a page with a detailed breakdown of the associated cloud resources, and the cost of each. You will also see that each resource has an option for <strong>Allocate.</strong> Clicking this will allow you to assign that resource to a cost center and actually charge the cost of that resource back to the department or business unit that consumed it. In addition, all future costs associated with that unallocated resource will automatically be added to the cost center that you just manually specified.

![](https://video.udacity-data.com/topher/2020/September/5f6946bd_beam-labs-chargeback-3-details-view/beam-labs-chargeback-3-details-view.png)

![](https://video.udacity-data.com/topher/2020/September/5f6946d2_beam-labs-chargeback-4-allocate-to-cost-center/beam-labs-chargeback-4-allocate-to-cost-center.png)

## Quiz: Cost Centers and Business Units

### QUIZ QUESTION
What is the difference between a cost center and a business unit?

* A cost center is a collection of resources within a single or multiple cloud accounts. A business unit is a collection of cost centers.

## Budgets and Budget Alerts

[![IMAGE ALT TEXT](https://raw.githubusercontent.com/ARBUCHELI/HYBRID-CLOUD-ENGINEER-NANODEGREE-PROGRAM-PART-2/main/images/532.jpg)](https://www.youtube.com/watch?time_continue=160&v=b5wnSXGEvPE&feature=emb_logo)

Budgets can be defined at a highly granular level. While a financial admin’s focus is likely to be cost centers and business units, any consumer of cloud resources - like engineers - would be interested in setting up budgets and alerts for resources they consume without having to tie it into a cost center.

For example, an engineer might want to set a budget alert for only the bare metal instances that are consumed in the Nutanix hybrid cloud without having to worry about what cost center that should be a part of and what additional resources should be there in the cost center.

To actually create a budget, navigate to the Budget page in Beam. If you haven’t defined any budgets in Beam before, you will be prompted to create one. To create a new budget, click Create a Budget.

On the first page, you’ll be prompted to select a type - Scope, Business Unit/Cost Center, or Custom. For this example, we’re going to create a custom budget, so we’ll select Custom and click Next.

![](https://video.udacity-data.com/topher/2020/September/5f6946f4_beam-labs-budget-2-select-type/beam-labs-budget-2-select-type.png)

On the second page for a custom budget, you’ll be prompted to define a resource group. This grouping, called a scope, is what Beam will track costs against. Here, you have the option to choose a cloud, accounts, services, regions, and tags. You can choose any combination of these items; it is not necessary to select all in order to create a budget. So you can, for example, set up a budget for the EC2 service in the US East region without specifying any tags.

After you make your resource selections, click Save. You will have the option to review your defined scope and edit it if needed. Once your scope changes are complete, click Next.

![](https://video.udacity-data.com/topher/2020/September/5f69470c_beam-labs-budget-3-create-resource-group/beam-labs-budget-3-create-resource-group.png)

![](https://video.udacity-data.com/topher/2020/September/5f694723_beam-labs-budget-4-define-resource-group/beam-labs-budget-4-define-resource-group.png)

On the third page, you will be presented with the option to define and allocate your budget. Here, you can name your budget, choose the financial year to which the budget applies, and select your allocation method. If you select Automatic Allocation, Beam will use your spending data to allocate a budget. If you select Manual Allocation, you can specify the annual budget, allocate that annual budget to each quarter of the year, or click a single link to distribute your annual budget equally.

Once you have made your allocation, click Next.

![](https://video.udacity-data.com/topher/2020/September/5f69473f_beam-labs-budget-5-allocate-budget/beam-labs-budget-5-allocate-budget.png)

The final step in the process is to define and add alerts. This is the only step of the process that you can skip and return to later if needed. You can set daily, weekly, or monthly budget limit alerts for resource groups to track the cloud budget. If the threshold for cloud expenses is exceeded, Beam will send an email to your registered email address. Multiple email addresses can be specified if you want multiple people to receive alerts.

If you do not want to create alerts at the moment, click Skip Alert & Save. If you do want to create an alert, click Create in the Actions column, select the period from the drop down, and then specify a threshold. Click Save to save your alert, and then Save again to save your Budget and all of the associated parameters.

![](https://video.udacity-data.com/topher/2020/September/5f694759_beam-labs-budget-6-add-alerts/beam-labs-budget-6-add-alerts.png)

![](https://video.udacity-data.com/topher/2020/September/5f69476f_beam-labs-budget-7-configure-alerts/beam-labs-budget-7-configure-alerts.png)

## QUIZ QUESTION
What sort of frequency can you define for budget alerts?

* Daily, Weekly, Monthly

## Custom Reports

[![IMAGE ALT TEXT](https://raw.githubusercontent.com/ARBUCHELI/HYBRID-CLOUD-ENGINEER-NANODEGREE-PROGRAM-PART-2/main/images/532.jpg)](https://www.youtube.com/watch?v=JOlYlPDmb5k&feature=emb_logo)

Beam allows you to create highly customizable cost reports that you can schedule to be delivered to specific users daily, weekly, or monthly. As with other capabilities that we’ve discussed so far — like analysis, saving, and purchases — reports have their own sub-section of the Beam interface as well. To access it, click the main menu icon at the top left of the screen and select <strong>Reports.</strong>

![](https://video.udacity-data.com/topher/2020/September/5f694793_reports-overview/reports-overview.png)

As with other subsections, the first thing you’ll see is an overview dashboard that summarizes key reports at a very high level. Among other things, you’ll see widgets for Cost Report by Account; a collection of EC2 reports (since we are looking at the AWS reports screen in this example) such as RI recommendation, RI utilization, cost by instance type and so on. On this screen, you can also use the filter menu near the top right to view daily, weekly, or monthly reports.

Then, at the top left of the screen, you’ll see two additional options — Scheduled and Custom. Clicking Scheduled will display a page with scheduled reports. Here, you can view reports that have been scheduled, as well as disable, edit, or delete reports.

![](https://video.udacity-data.com/topher/2020/September/5f6947ac_reports-scheduled/reports-scheduled.png)

Finally, the third tab will allow you to view all custom reports that have been created and create new custom reports as needed. From the custom reports page, you can run a report immediately if you need to, or perform additional actions such as viewing, editing, downloading, scheduling, sharing, or deleting any of the custom reports in the list.

![](https://video.udacity-data.com/topher/2020/September/5f6947c5_reports-custom-page/reports-custom-page.png)

Creating a new custom report, like most creation processes with Nutanix software, largely involves filling out a form. These reports are highly customizable across 10 dimensions and have many options for filters including services, accounts, availability zones and tags.

![](https://video.udacity-data.com/topher/2020/September/5f6947e2_reports-create-custom/reports-create-custom.png)

Once you specify your dimensions and choose your metrics (cost and usage), time, and filters, you simply need to click <strong>Generate</strong> to set up, run, and save your custom report. For example, you could create a custom report with dimensions selected for “Service” and “Regions”. This will create a report of spending on each AWS service in each AWS region. You can then filter the data out to show only the daily cost for a particular AWS service (such as EC2) grouped together by regions.

The following image shows what a custom report for the EC2 service, with daily cost grouped by region, would look like.

![](https://video.udacity-data.com/topher/2020/September/5f6947fb_beam-labs-custom-report-daily-ec2-spend-by-region/beam-labs-custom-report-daily-ec2-spend-by-region.png)

## Exercise: Cost Center Reporting

Now that we know what individual VMs cost to run on Nutanix, we can create cost views that aggregate consumption across various VMs and clusters in a Nutanix private cloud, and also across multiple clouds - private and public.

* 1. In a new web browser tab, go to https://beam.nutanix.com and click Sign in with My Nutanix.

* 2. Use **hce-beam##@udacity.com as your email address. Replace ## with your day of birth. E.g., if your birthday is January 5,that equates to [hce-beam05@udacity.com]. ## will have values from 01 to 31. (If for any reason your login does not work, you may try a value of ## = 32, 33 or 34). The password will be Nutanix1234@**.

### Creating a Cost Center

* 3. Click Entities > Chargeback. You may notice some cost centers previously created by other users.

* 4. Select Create then Cost Center.

* 5. In the Name field, use the initials of your full name, then -udacity-hce for the name. Example: abc-udacity-hce. Click Define Cost Center.

* 6. Fill out the following fields:

* o Cloud: Nutanix

* o Parent Account: Beam Lab Nutanix Account

* o Sub Accounts: Search for the last four digits of the Cluster ID you saved to your Workspace folder..

* o Key Set 1: nx:App

* o Value Set 1: Select any available_ VDI###_value

Note: The ### will be a three-digit number. You may select any number between 001 to 100. This is being done to provide a unique key-value pair for each lab attendee because each key-value pair can only be in a unique cost center to avoid double counting of resource costs in different cost centers.

* 7. Click Save Filter to save the key-value pair used as a filter.

Note: Each Key-Value pair can only be added to a unique Cost Center. If you get an error message when you define your Key-Value pair, it is likely because another user already added that Key-Value pair to their Cost Center. Please select a different VDI### value.

* 8. Now make this cost center truly a multicloud cost reporting view by adding another key-value pair from a public cloud. Click Add filter and fill out the following fields:

* o Cloud: Azure

* o Parent Account: Beam Lab Azure Enrollment

* o Sub Accounts: Xi Beam Cost Governance.

* o Key Set 1: Owner

* o Value Set 1: Select any available beam-lab-### value. Use the same ### value that you used when defining the nx:app and VDI### tag.

* 9. Click Save Filter and then Save Definition to save the definition of the cost center and Save Cost Center to exit the view and go back to the Chargeback screen.

You have now created a cost center which will aggregate costs from all Nutanix private cloud resources carrying the tag key nx:App and tag value VDI### along with Azure public cloud resources carrying the tag key Owner and tag value beam-lab-###. This gives you great flexibility to create hybrid and multicloud cost reports which can be used for the purpose of Chargeback.

This cost center definition can also be stretched to include other supported public clouds such as AWS as an additional cloud in the same cost center view.

### Chargeback & Budgeting

### Chargeback Unallocated Spend

Not all cloud resources may be tagged with the key-value pairs that you specify in cost centers. In fact, not all cloud resources are taggable. Many times, you will find that there will be spending that did not fit a cost center definition. In order to ensure accurate financial accountability (ensuring that all costs spent by a user, department, team, etc. are captured accurately), a hybrid cloud engineer should ensure that any unallocated spending, due to some resources not being covered in a cost center definition, is also accounted for and allocated to the appropriate cost center. This can be captured through Chargeback.

* 1. From the Chargeback page, click Unallocated at the upper right.

* 2. Under Unallocated Costs, click on any cluster that is shown as having unallocated costs and then click View Details to see the details of spend on this cluster that did not get allocated to any cost center.

Note: If you might be taking this lab on the first day of a month then there may be some time lag in cost reporting, and you may not see any unallocated spend. If so, switch the monthly view to the prior month using the drop-down menu in the top right corner which shows the month that has been selected. By default, it will show the current month, but you can switch it to a prior month to see unallocated spending from a prior month.

* 3. If you find any unallocated spend from some VMs. Click Allocate for the first Resource ID in the list and choose your cost center created earlier.

* 4. You can also split the spend across multiple cost centers or allocate all VMs to a cost center. Select the check boxes for the first three Resource IDs and click Bulk Allocate at the upper right.

* 5. In the Select a cost center dialog box, select your cost center from the Cost Center Name pulldown menu. Leave the Percent Split at 100 and click Allocate Resources. The results may take up to 24 hours to populate.

You only need to do this once. Any future spending by the same VM will be automatically allocated to that cost center.

### Budget Alerts

In this exercise you will define a budget for a cost center and set up a related alert.

* 1. Go to Entities > Budget tab and click Create a Budget.

* 2. Select Business Unit/Cost Center based Budget and click Next.

NOTE: Beam also allows you to create a custom resource group using a combination of accounts, services, and tags, and then set up budget alerts on the custom resource group.

* 3. Select the Cost Center you created in the previous exercise. Click Next.

* 4. Select Manual Allocation. This will allow you to customize values for the budget at a yearly, quarterly or monthly level.

* 5. In the Set Annual Budget field, enter $100,000. It will be allocated equally to each month. If you like, you can customize this for each quarter or each month. Click Next.

* 6. Click Create next to Quarterly Budget Alerts.

* 7. In the Budget Alert dialog box, set a Threshold value of 85% and click Save.

* 8. Add your email address under Alert Notifications (hit the enter keyboard key after entering your email address to save it in the email field). Click Save.

You have now created a budget alert to be notified when spending in your cost center goes above a certain threshold relative to your configured quarterly budget.

### Public Cloud Cost Savings

### AWS Account Configuration

This section will walk you through how Beam identifies cost savings for public clouds like AWS. To configure Beam with AWS, customers will need access to their AWS Payer account. Any Linked accounts associated with the Payer account will automatically be identified by Beam.

* 1. From the Entities menu, go to Dashboard and then at the upper right, click Nutanix and in the view selector , select AWS.

* 2. In the Select Payer Account column, select Beam Lab Payer Account.

Note: For the lab environment, an AWS Payer Account named Beam Lab Payer Account has already been configured. You may familiarize yourself with the configuration steps

* 3. From the Entities , select Configure > AWS Accounts. You will see the Beam Lab Payer Account that has been configured for this lab. Click Manage.

* 4. In the Beam Lab Payer Account , you will see all the associated linked accounts that have been identified by Beam. To find maximum cost savings, it is recommended to run the following configuration steps for the Payer account and each Linked account under that Payer account. For this lab, we will only concern ourselves with the Payer account. At the upper right, click on Edit at the Payer account level.

* 5. From this page, customers will enter their AWS Cost and Usage Report (CUR) details. Beam identifies cost spending based on the CUR data at the payer account level. The CUR also includes spending data for all linked accounts. Observe that the CUR name and the AWS S3 storage bucket name where the CUR resides have been configured in the lab setup. Customers can specify their account name, whether they want to give read-only or read and write access to Beam and generate a CloudFormation Template. They will run the CloudFormation Template by logging into their AWS Payer or Linked accounts to complete the setup. This will create an AWS access role for Beam,allow Beam to read their billing data from the CUR and read their log metrics and resource utilization such as CPU, memory, disk usage, etc. Beam uses all that information to identify spending and make cost saving recommendations. If they give write access, they will be able to take various one-click actions from the Beam console to act upon Beam’s cost saving recommendations.

* 6. At the upper right, click X to close the Configurations screen

Note: It takes Beam up to 24hrs to process public cloud billing data and start making cost saving recommendations. For this lab, you can familiarize yourself with what these recommendations look like.

### Eliminate Unused Resources

Beam identifies cloud resources that have been unused for an extended period and can be eliminated to save on costs.

* 1. Click on the Entities menu and click on Save. If you are presented with a popup, select the Beam Lab Payer Account in the Select Payer Account column, then click Beam Lab Payer Account in the Select Linked Account column, otherwise, you should be in the Overview tab.

* 2. Click on the Eliminate tab. Here you will see various cloud resources identified by Beam that have not been used to satisfy the criteria for unused resources in the Beam cost policy.

* 3. Familiarize yourself with the default Beam cost policy. From the Entities menu, select Configure > Cost Policy.

* 4. Click View on the System Policy-AWS row. It will show the Beam cost policy used to identify unused and underutilized resources. After reviewing, click X to close the policy and then click the Entities menu and select Save and then Eliminate tab to go back to the Eliminate view.

* 5. In the Eliminate tab, locate Unused ELB and click View List to see more details about the unused AWS Elastic Load Balancers identified by Beam.

* 6. You will see details of unused ELBs including their resource ID, the cloud account and associated cost savings by their elimination. If Beam was given write access during AWS account configuration, customers could take one-click actions to eliminate unused ELBs and immediately realize cost savings. The lab environment does not have this feature enabled.

### Right-size Underutilized Resources

Beam also identifies cloud resources that are not being used optimally and therefore are underutilized. Optimizing the size of these resources can add to cost savings. Beam cost policy defines the criteria considered when identifying underutilized resources. These can be modified by customers.

* 1. Click on the Optimize tab. You will see various cloud resources identified by Beam that satisfy the underutilized resource criteria in the Beam cost policy.

* 2. Locate Underutilized EC2 and click View List to see more details about the underutilized AWS Elastic Compute Cloud instances identified by Beam.

* 3. Click in the row of any one of the displayed items. You will see details of the EC2 instance including their resource ID, the cloud account and associated cost savings by changing their size from their current size to a downgraded size recommended by Beam. These recommendations are made based on CPU utilization and the optimization rules configured in Beam policy. Click in the row again to hide the summary. Click How to optimize? to show the recommendations and instructions to implement the optimizations.

* 4. Close the How to optimize? popup.

## Smarter Reserved Instance Purchases

Beam also makes recommendations on the most optimal EC2 Reserved Instance (RI) purchases based on customer’s usage history. By purchasing RIs using Beam's recommendations, customers can save a huge amount over their on-demand instance spend.

* 1. From the Entities menu, select Purchase > Overview tab. You will see the current amount of EC2 RI coverage in the AWS account as well as Beam's recommendations for new RI purchases. Click on View All Recommendations at the lower right, to see all RI purchase recommendations

* 2.You will see Beam’s EC2 RI Purchase recommendations and the associated cost savings by switching to RI instead of on-demand pricing. Beam makes these RI recommendations by first identifying the EC2 instances that are running continuously over a lookback period (default value is 14 days). Beam then normalizes the size of those EC2 instances and calculates the amount of normalized instances that can be optimally covered by an RI purchase. Click on any of the RI recommendations to see their details.

* 3. In the RI details view, you will see the EC2 instance utilization chart showing the number of instances of the same type and how they have changed over the lookback period. Beam identifies the minimum number of instances so the RI purchase will always cover at least the minimum number of instances that are running continuously. Beam also provides a Breakeven Analysis chart that shows the time period it would take for the higher upfront cost of an RI purchase to break-even vs on-demand costs. Customers can then decide if they should purchase this RI if they expect to use these EC2 instances for the duration of the break-even period.

By acting upon all Beam's cost saving recommendations, Beam’s public cloud customers will be able to save 35% or more on their spend within the first few months of using Beam.

* 4. Logout by clicking the username HCE Beam## and selecting Log out.

This completes the Cloud Cost Governance exercise.

## Exercise Solution: Cost Center Reporting

[![IMAGE ALT TEXT](https://raw.githubusercontent.com/ARBUCHELI/HYBRID-CLOUD-ENGINEER-NANODEGREE-PROGRAM-PART-2/main/images/536.jpg)](https://www.youtube.com/watch?v=38dF1hDQLA8&feature=emb_logo)

## Glossary

### Amortized Cost Logic: 
A type of cost reporting which is based on accrual-based accounting.

### Absolute Cost Logic: 
A type of cost reporting which is based on cash-based accounting.

### Automated scheduling policy: 
A policy that shuts down compute and storage instances when they are not needed and brings them up when you are ready to use them again.

### Blended Cost: 
A cost reporting option in Xi Beam. If you select this option, Beam reports the cost of resources based on the average cost of usage across the consolidated billing family.

### Business Unit:
In Xi Beam, a business unit is defined as a collection of cost centers.

### Chargeback: 
A process through which enterprises can apportion cloud costs to different business units or cost centers. This could be for a team, a project, a region, or a department.

### Cloud Cost Monitoring & Optimization (CCMO) tools: 
Software that can help you visualize resources by groups and departments, empowering you to manage their usage and enforce policies based on allocated budgets.

### Cost Center:
In Xi Beam, a cost center is a collection of resources within a single or multiple cloud accounts. You can assign resources to a cost center based on cloud accounts and tags. You can either allocate a complete account or resources within an account to a cost center.

### Cost Governance: 
The process and activities involved in planning, managing, and controlling the budget of a business.

### Continuous monitoring:
A component of optimal cloud management which involves continuously monitoring resource utilization such as CPU, memory, disk usage, and so on.

### Continuous optimization: 
A component of optimal cloud management in which administrators implement policies to resize resources that are too bulky for what they are being used for.

### Reserved instances:
Typically compute and database services that are available at significant discounts if you commit to them for a duration of one year or longer.

### Scope: 
A scope is a logical group of your cloud resources that provides you with a custom view of those cloud resources.

### Unblended Cost: 
A cost reporting option in Xi Beam. If you select this option, Beam reports the cost of resources based on usage.

### Xi Beam: 
Xi Beam by Nutanix is a software-as-a-service product that helps customers with cost governance for both their public and private clouds. Beam’s cost optimization capabilities help identify cost saving opportunities in public clouds, and also enable chargeback and budgeting across public and private clouds.
















# Adaptation as a repository: Andrés R. Bucheli.
