# Kubernetes Architecture & Components

![Kubernetes Architecture Diagram]([images/architecture.png](https://github.com/chavhanshanku7/TWS-Kubernetes-Challenge/blob/main/Kubernetes%20Architecture%20Diagram.PNG))

# Master Node Components
## 1. API Server
  The API server is a component of the Kubernetes control plane that exposes the Kubernetes API. The API server is the front end for the Kubernetes control plane.
  The main implementation of a Kubernetes API server is kube-apiserver.
  kube-apiserver is designed to scale horizontally that is, it scales by deploying more instances. You can run several instances of kube-apiserver and balance 
  traffic between those instances.
  
## 2. etcd
  Consistent and highly-available key value store used as Kubernetes' backing store for all cluster data.
  If your Kubernetes cluster uses etcd as its backing store, make sure you have a back up plan for the data.
  
## 3. Scheduler
  Control plane component that watches for newly created Pods with no assigned node, and selects a node for them to run on.
  Factors taken into account for scheduling decisions include: individual and collective resource requirements, hardware/software/policy constraints, affinity and    anti-affinity specifications, data locality, inter-workload interference, and deadlines.
  
## 4. Controller Manager
  Control plane component that runs controller processes. Logically, each controller is a separate process, but to reduce complexity, they are all compiled into a    single binary and run in a single process.

  There are many different types of controllers. Some examples of them are:

  • **Node Controller:** Responsible for noticing and responding when nodes go down.<br>
  • **Job Controller:** Watches for Job objects that represent one-off tasks, then creates Pods to run those tasks to completion.<br>
  • **EndPointSlice Controller:** Populates EndpointSlice objects (to provide a link between Services and Pods).<br>
  • **ServiceAccountController:** Create default ServiceAccounts for new namespaces.<br>

## 5. Cloud Controller Manager
  A Kubernetes control plane component that embeds cloud-specific control logic. The cloud controller manager lets you link your cluster into your cloud provider's   API, and separates out the components that interact with that cloud platform from components that only interact with your cluster.

  The cloud-controller-manager only runs controllers that are specific to your cloud provider. If you are running Kubernetes on your own premises, or in a learning   environment inside your own PC, the cluster does not have a cloud controller manager.

  As with the kube-controller-manager, the cloud-controller-manager combines several logically independent control loops into a single binary that you run as a       single process. You can scale horizontally (run more than one copy) to improve performance or to help tolerate failures.

  The following controllers can have cloud provider dependencies:

  • **Node Controller:** For checking the cloud provider to determine if a node has been deleted in the cloud after it stops responding.<br>
  • **Route Controller:** For setting up routes in the underlying cloud infrastructure.<br>
  • **Service Controller:** For creating, updating and deleting cloud provider load balancers.<br>
  
## Worker Node Components




