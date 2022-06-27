# Awesome Cloud Native

> Cloud native infrastructure is infrastructure that is hidden behind useful abstractions, controlled by APIs, managed by software, and has the purpose of running applications. Running infrastructure with these traits gives rise to a new pattern for managing that infrastructure in a scalable, efficient way.
 
5 cloud native principles 

* Scalable 
* Resilient 
* Manageable 
* Observable 
* Automated 


A cloud native application is engineered to run on a platform and is designed for: 

* **Resiliency**  - Embraces failures instead of trying to prevent them; it takes advantage of the dynamic nature of running on a platform. Resilience (roughly synonymous with fault tolerance) is a measure of how well a system withstands and recovers from errors and faults. A system can be considered resilient if it can continue operating correctly—possibly at a reduced level—rather than failing completely when some part of the system fails.
* **Agility** allows for fast deployments and quick iterations.  
* **Operability** adds control of application life cycles from inside the application instead of relying on external processes and monitors.  
* **Observability** provides information to answer questions about application state. 

## Cloud Transformation

Successful transformation programs are business-driven. They have clear governance of key milestone objectives and success metrics coupled with a people strategy that accommodates a variety of organizational / team levels of cloud expertise. Successful cloud transformation programs enable teams to work and collaborate using agile principles to improve collaboration and joint prioritization. An agile approach breaks down large tasks (such as enterprise migration) into manageable, iterative pieces of work delivered and measured incrementally. 

![Cloud Agile Transformtion](https://docs.aws.amazon.com/whitepapers/latest/cloud-driven-enterprise-transformation-on-aws/images/CloudTransformation2.png)

[Transformation Domains](https://docs.aws.amazon.com/whitepapers/latest/overview-aws-cloud-adoption-framework/images/cloud-adoption-1.png)

[Transformation Foundation Capabilities](https://docs.aws.amazon.com/whitepapers/latest/overview-aws-cloud-adoption-framework/images/cloud-adoption-2.png)

[Platform Capabilities](https://docs.aws.amazon.com/whitepapers/latest/overview-aws-cloud-adoption-framework/images/cloud-adoption-8.png)

[Cloud Security](https://docs.aws.amazon.com/whitepapers/latest/overview-aws-cloud-adoption-framework/images/cloud-adoption-9.png)

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

[Istio](https://istio.io/latest/) is a control plane with [sidecar pattern](https://blog.envoyproxy.io/service-mesh-data-plane-vs-control-plane-2774e720f7fc) [architecture](https://istio.io/latest/docs/ops/deployment/architecture/) that uses [Envoy](https://www.envoyproxy.io/) [proxies](https://blog.envoyproxy.io/introduction-to-modern-network-load-balancing-and-proxying-a57f6ff80236) for its data plane. 

[Jaegar](https://www.jaegertracing.io/)  

[Grafana](https://grafana.com/)

[AWS Managed Service for Grafana](https://aws.amazon.com/grafana/?nc2=type_a) With Amazon Managed Grafana, you can analyze your metrics, logs, and traces without having to provision servers, configure and update software, or do the heavy lifting involved in securing and scaling Grafana in production 

[Prometheus](https://prometheus.io/)  

[AWS Managed Service for Prometheus](https://aws.amazon.com/prometheus/) Amazon Managed Service for Prometheus automatically scales the ingestion, storage, alerting, and querying of operational metrics as workloads grow or shrink, and is integrated with AWS security services to enable fast and secure access to data – not available in Canada central – how to use? Seems very very expensive.  

[GCP Managed Service for Prometheus](https://cloud.google.com/stackdriver/docs/managed-prometheus) Fully managed Prometheus compatible monitoring stack with default two year retention and global queries over regionalized data – lowered pricing for high tier usage 

[AWS App Mesh](https://aws.amazon.com/app-mesh/?aws-app-mesh-blogs.sort-by=item.additionalFields.createdDate&aws-app-mesh-blogs.sort-order=desc&whats-new-cards.sort-by=item.additionalFields.postDateTime&whats-new-cards.sort-order=desc) uses Envoy (fully managed servce)  

Anthos Service Mesh[https://cloud.google.com/anthos/service-mesh) uses Istio (fully managed service) - opinions 

[Open Telemetry](https://opentelemetry.io/)

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

 

