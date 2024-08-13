# Kubernetes Architecture & Components

![Kubernetes Architecture Diagram]([images/architecture.png](https://github.com/chavhanshanku7/TWS-Kubernetes-Challenge/blob/main/Kubernetes%20Architecture%20Diagram.PNG))

## Master Node Components
* API Server
  The API server is a component of the Kubernetes control plane that exposes the Kubernetes API. The API server is the front end for the Kubernetes control plane.
  The main implementation of a Kubernetes API server is kube-apiserver.
  kube-apiserver is designed to scale horizontally—that is, it scales by deploying more instances. You can run several instances of kube-apiserver and balance 
  traffic between those instances.
  
* etcd
* Scheduler
* Controller Manager
* Cloud Controller Manager
  
## Worker Node Components




