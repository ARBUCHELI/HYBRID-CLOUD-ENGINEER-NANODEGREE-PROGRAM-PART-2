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




# Adaptation as a repository: Andrés R. Bucheli.
