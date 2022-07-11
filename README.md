# Awesome Cloud Native

> Cloud native infrastructure is infrastructure that is hidden behind useful abstractions, controlled by APIs, managed by software, and has the purpose of running applications. Running infrastructure with these traits gives rise to a new pattern for managing that infrastructure in a scalable, efficient way.
 

A cloud native application should use **automation** to **scale** workloads that have been designed for: 

* **Resiliency**  - Embraces failures instead of trying to prevent them; it takes advantage of the dynamic nature of running on a platform. Resilience (roughly synonymous with fault tolerance) is a measure of how well a system withstands and recovers from errors and faults. A system can be considered resilient if it can continue operating correctly—possibly at a reduced level—rather than failing completely when some part of the system fails.
* **Agility** allows for fast deployments and quick iterations.  
* **Operability** adds control of application life cycles from inside the application instead of relying on external processes and monitors.  
* **Observability** provides information to answer questions about application state. 

## Cloud Transformation

Successful [transformation programs](https://aws.amazon.com/blogs/enterprise-strategy/802-2/) are business-driven. They have clear governance of key milestone objectives with a [cloud operating mode](https://docs.aws.amazon.com/whitepapers/latest/building-cloud-operating-model/building-cloud-operating-model.html) that builds transparent success metrics coupled with a people strategy that accommodates a variety of organizational / team levels of cloud expertise. Successful cloud transformation programs enable teams to work and collaborate using agile principles to improve collaboration and joint prioritization. An agile approach breaks down large tasks (such as enterprise migration) into manageable, iterative pieces of work delivered and measured incrementally. 

![Cloud Agile Transformtion](https://docs.aws.amazon.com/whitepapers/latest/cloud-driven-enterprise-transformation-on-aws/images/CloudTransformation2.png)

Successful organizations utlize cloud transformation to: 

* align IT portfolio to business priorities
  * Modernize what matters
  * prioritize what moves when/how (l&s/managed/cloud-native/microservice)
* accelerate digital transformation 
* Increase productivity of engineering teams 
* Automate 
* address technical debt 
* Migrate simpler cases while long-planner tough applications 

![Cloud Transformation FlyWheel](https://docs.aws.amazon.com/whitepapers/latest/cloud-driven-enterprise-transformation-on-aws/images/CT3.jpg)

![Transformation Domains](https://docs.aws.amazon.com/whitepapers/latest/overview-aws-cloud-adoption-framework/images/cloud-adoption-1.png)

![Transformation Foundation Capabilities](https://docs.aws.amazon.com/whitepapers/latest/overview-aws-cloud-adoption-framework/images/cloud-adoption-2.png)

![Platform Capabilities](https://docs.aws.amazon.com/whitepapers/latest/overview-aws-cloud-adoption-framework/images/cloud-adoption-8.png)

![Cloud Security](https://docs.aws.amazon.com/whitepapers/latest/overview-aws-cloud-adoption-framework/images/cloud-adoption-9.png)

![Cloud Governance](https://docs.aws.amazon.com/wellarchitected/latest/management-and-governance-guide/images/how-to-prepare-aws-environments.png)

![image](https://user-images.githubusercontent.com/64801585/177202204-019e8ffd-5ea5-40ad-b467-b47705fba85c.png)


![image](https://user-images.githubusercontent.com/64801585/177121229-d96ebef9-985d-456d-968e-818ddd8d2dbd.png)

![image](https://user-images.githubusercontent.com/64801585/177121750-e1e13ffd-0c16-45f2-9499-0f86b1f2c3b0.png)

![image](https://user-images.githubusercontent.com/64801585/177122485-6e7ca1b5-c1d7-4e24-8e2a-a7676d4ba13b.png)


* [GCP Landing Zones](https://cloud.google.com/architecture/landing-zones)

* [Aws Control Tower](https://aws.amazon.com/controltower/?control-blogs.sort-by=item.additionalFields.createdDate&control-blogs.sort-order=desc)
* [Aws Organizations](https://aws.amazon.com/organizations/)


## FinOps

### FinOps References 

[GCP Unlocking Value of FinOps](https://services.google.com/fh/files/misc/unlocking_the_value_of_cloud_finops_with_a_new_operating_model_whitepaper.pdf)

[Google Guide to Financial Governance in the Cloud](https://cloud.google.com/files/guide-to-financial-governance.pdf)

[Getting Started on FinOps in GCP](https://cloud.google.com/resources/cloud-finops-getting-started-whitepaper)

[GCP Maximize Business Value with Cloud FinOps](https://cloud.google.com/resources/cloud-finops-whitepaper)

## Cloud DevSecOps

> DevSecOps advances the growing philosophy and sentiment that reliance upon bolt-on or standalone monolithic cybersecurity platforms is incapable of providing adequate security in today’s operational environments. Cybersecurity tooling that is fully isolated from the development and operational environments are reactive at best, whereas integrated automated tooling with the software factory is proactive. 

We can measure the success or failure of our DevSecOps transformation via the 4 key metrics: 

* **Deployment Frequency** – cycle Time, planning to production.
* **Lead Time** – the measurement between commit time to production deployment.
* **Mean Time to Resolution (MTTR)** – how long to get your code back up and running, if there is an incident.
* **Change Failure Rate (CFR)** – % changes going into production that require rework.

![devSecOps](https://github.com/Ramb0a/awesome-cloud-native/blob/main/devSecOps.png)

DevSecOps is eight phases complimented by specific cybersecurity activities: 
* **Plan**
* **Develop** 
* **Build** 
* **Test**
* **Release** 
* **Deliver** 
* **Deploy**
* **Operate**
* **Monitor** 

Security Scanning Requirements:

* **Static Application Security Testing (SAST)** should be performed early and often against all files containing source code or binaries.
  * Application is security tested from the inside out
  * Does not need to execute the application.
  * Can't discover run-time vulnerabilities since analysis happens prior to execution  
* **Dynamic Application Security Testing (DAST)** should be performed on a running application in an environment similar to production
  * Application is security tested from the outside in 
  * Hacker approach security testing 
  * Does not require source code or binaries 
  * Analyses by executing application 
  * typically most useful for web applications/web services  
* Container Image Scanning
* Infrastructure-as-code (IAC) scanning
* Secret detection


### Zero Trust

> Zero Trust must be the target security model for cybersecurity adopted by DevSecOps platforms and the teams that use those platforms. 

**Behaviour Detection** - trigger an actionable and logged alert that conveys I saw something anomalous

**Behavioud Prevention** -  triggers an actionable and logged alert, but also either proactively prevent or immediately terminates anomalous behaviors and conveys I inhibited something anomalous.



## Migation Patterns 

![image](https://user-images.githubusercontent.com/64801585/177016575-7925f5db-7a68-4d88-aebc-275a1ed502a3.png)


The choice is not between moving applications to the cloud “as is” or full refactoring to enable cloud-native capabilities. There is a spectrum of options in-between. Companies who move fastest empower teams to evaluate trade-offs, document their decisions, move quickly, and use data to measure performance and adjust.

Companies that do not engage all aspects of their organization to accelerate through the most complex phase of dual operations (on-premises and on cloud) often stall early in the transition, diminish the business case, and miss the opportunity to capture the value of cloud innovation.

![image](https://user-images.githubusercontent.com/64801585/176884107-7b107564-f922-4fb4-87e2-ab4c23d601d1.png)

![image](https://user-images.githubusercontent.com/64801585/177122571-39d0a980-1427-4c95-a766-d9d420f3bd96.png)


### Life & Shift

Migrating applications to cloud, even in a “like for like” architecture approach with minimal optimization or refactoring, still requires a thoughtful “full stack” design. This entails addressing all the design elements, including:

* Infrastructure design
* Application architecture
* Testing suite
* Deployment processes
* Resiliency considerations
* Operational capabilities


## Containers

* [Open Container Initiaitive](https://opencontainers.org/)
* [Podman](https://podman.io/)

## Cloud Compute 

A known problem in cloud compute is the [Noisy Neighbor](https://docs.microsoft.com/en-us/azure/architecture/antipatterns/noisy-neighbor/noisy-neighbor) problem in multi-tenancy 
 

### AWS 

Compute seems to now fall under the [Nitro System](https://aws.amazon.com/ec2/nitro/) - a combination of dedicated hardware and lightweight [hypervisor](https://www.vmware.com/topics/glossary/content/hypervisor.html).

AWS most state of the art processors are the [Graviton](https://aws.amazon.com/ec2/graviton/) which use 64-bit Arm [Neoverse cores](https://www.arm.com/products/silicon-ip-cpu/neoverse/neoverse-n1) optimized for handling a wide range of cloud-native workloads.

Compute Instances are of several types: 

* Fixed Performance Instances – for consistently high CPU performance for applications 
* [Burstable Performance Instances](https://aws.amazon.com/ec2/instance-types/#Burstable_Performance_Instances) - provide a baseline level of CPU performance with the ability to burst above the baseline. 
* [Spot instances](https://aws.amazon.com/ec2/spot/) 
  * AWS: EKS Fargate: Currently does not support spot instances - source (June, 2022). Spot instances are however supported in ECS, EKS (standard) and ECS Fargate. 

## Service Mesh 

[Service mesh](https://d1.awsstatic.com/whitepapers/using-service-meshes-in-aws.pdf?did=wp_card&trk=wp_card) is network communication between the parts of an application comprised of a control plane and a data plane.

* **Data plane** is proxies sitting next to your applications or services, intercepting any network traffic that is under the management of the [proxies](https://blog.envoyproxy.io/introduction-to-modern-network-load-balancing-and-proxying-a57f6ff80236)
* **Control Plane** manages the configuration of the the configuration of the proxies of the data plane usually through an API.

Service meshes should not be the first project you get into in your cloud journey. if you have a monolith without a path to microservices, you don’t need a service mesh.

### Service Mesh Tools

* [Istio](https://istio.io/latest/) is a control plane with [sidecar pattern](https://blog.envoyproxy.io/service-mesh-data-plane-vs-control-plane-2774e720f7fc) [architecture](https://istio.io/latest/docs/ops/deployment/architecture/) that uses [Envoy](https://www.envoyproxy.io/) proxies for its data plane. 
* [Jaegar](https://www.jaegertracing.io/)  
* [Grafana](https://grafana.com/)
* [AWS Managed Service for Grafana](https://aws.amazon.com/grafana/?nc2=type_a) With Amazon Managed Grafana, you can analyze your metrics, logs, and traces without having to provision servers, configure and update software, or do the heavy lifting involved in securing and scaling Grafana in production 
* [Prometheus](https://prometheus.io/)  
* [AWS Managed Service for Prometheus](https://aws.amazon.com/prometheus/) Amazon Managed Service for Prometheus automatically scales the ingestion, storage, alerting, and querying of operational metrics as workloads grow or shrink, and is integrated with AWS security services to enable fast and secure access to data – not available in Canada central – how to use? Seems very very expensive.  
* [GCP Managed Service for Prometheus](https://cloud.google.com/stackdriver/docs/managed-prometheus) Fully managed Prometheus compatible monitoring stack with default two year retention and global queries over regionalized data – lowered pricing for high tier usage 
* [AWS App Mesh](https://aws.amazon.com/app-mesh/?aws-app-mesh-blogs.sort-by=item.additionalFields.createdDate&aws-app-mesh-blogs.sort-order=desc&whats-new-cards.sort-by=item.additionalFields.postDateTime&whats-new-cards.sort-order=desc) uses Envoy (fully managed servce)  
* [Anthos Service Mesh](https://cloud.google.com/anthos/service-mesh) uses Istio (fully managed service) - opinions 

[Open Telemetry](https://opentelemetry.io/)

[Service Mesh Interface](https://smi-spec.io/)

# Cloud SaaS Strategies

Multi-tenant SaaS products require a deep strategy for: 
* onboarding
* tenant isolation
* data partitioning
* tenant deployment pipeline
* observability

## [Tenant Isolation](https://d1.awsstatic.com/whitepapers/saas-tenant-isolation-strategies.pdf)

 enables SaaS providers to reassure customers that—even in a multitenant environment—their resources cannot be accessed by other tenants

the strategies and approaches to achieving this isolation are not universal.

AWS tenet isolation principles:
* Isolation is not optional 
* Authentication and authorization are not equal to isolation 
* Isolation enforcement should not be left to service developers
* If there’s not out-of-the box isolation solution, you may have to build it yourself 
* Isolation is not a resource-level construct
* Domains may impose specific isolation requirements

### Silo Isolation 

#### Pros
* **Supporting challenging compliance models** - dedicated model fits regulated industries 
*  **No noisy neighbor concerns** - no customers with potential of having their workloads impacted by the activity
of other tenants using the system
*  **Tenant cost tracking** - coarse-grained nature of the silo model provides us with a simple way to capture
and associate infrastructure costs with each tenant.
* **Limited blast radius** –  any failures that occur within a given tenant’s environment will likely be constrained to that environment.

#### Cons
* **Scaling issues** 
* **Costs** - with every tenant running in its own environment, we’re missing much of
the cost efficiency that is traditionally associated with SaaS solutions
* **Agility** - the highly decentralized nature of the silo model adds
complexity that impacts your ability to easily manage, operate, and support your
tenants
* **Onboarding automation** - The provisioning
of a new tenant will require the provisioning of new infrastructure and, potentially,
the configuration of new account limits. These added moving parts introduce
overhead that introduces additional dimensions of complexity into the overall
onboarding automation, enabling you to focus less time on your customers.
* **Decentralized management and monitoring** - While there are mechanisms that will enable you
to create an aggregate view of your tenants, the effort and energy needed to
build and manage this experience is more complex in a siloed model.


### Pool Isolation

the
efficiency, agility, and cost benefits of being able to have their tenants share some or all
of their underlying infrastructure.

even though this is a more challenging environment to isolation—
you cannot use this as a rationale to relax the isolation requirements of your
environment. If anything, these shared model increases the chance for cross-tenant
access and, as such, it represents an area that requires you to be especially diligent
about ensuring that resources are isolated.


#### Pros

* Agility 
* Cost efficiency 
* Simplified management and operations 
* Innovation 

#### Cons 

* Noisy neighbor
* Tenant cost tracking 
* Blast radius 
* Compliance pushback

## Bridge Model of Isolation

As you look at real application problems and
you decompose our systems into smaller services, you will often discover that your
solution will require a mix of the silo and pool models. This mixed model is what we
would refer to as a bridge model of isolation

your view of silo
and pool will be much more granular for environments that are decomposed into a
collection of services that have varying isolation requirements.

 

