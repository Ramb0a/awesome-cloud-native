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

Jaegar  

Grafana 

AWS Managed Service for Grafana With Amazon Managed Grafana, you can analyze your metrics, logs, and traces without having to provision servers, configure and update software, or do the heavy lifting involved in securing and scaling Grafana in production 

Prometheus  

AWS Managed Service for Prometheus Amazon Managed Service for Prometheus automatically scales the ingestion, storage, alerting, and querying of operational metrics as workloads grow or shrink, and is integrated with AWS security services to enable fast and secure access to data – not available in Canada central – how to use? Seems very very expensive.  

GCP Managed Service for Prometheus Fully managed Prometheus compatible monitoring stack with default two year retention and global queries over regionalized data – lowered pricing for high tier usage 

AWS App Mesh uses Envoy (fully managed servce)  

Anthos Service Mesh uses Istio (fully managed service) - opinions 

Open Telemetry 

 

