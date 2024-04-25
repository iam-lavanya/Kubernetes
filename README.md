# Kubernetes

 Kubernetes is an open-source container orchestration tool that is used to automate tasks such as the management, monitoring, scaling, and deployment of containerized applications. 

 ## Why Kubernetes
 
1. By default docker is single host(not cluster). Kubernetes by default it's a cluster.
2. Docker alone can't be used in production. We can use docker swarm for container orchestration but it's lacking enterprise features. Kubernetes provides great enterprise support with it's features.
3. Auto scaling
4. Auto healing
5. Service discovery

## K8S architecture :

It has a control plane and dataplane in which control plane is also called as master node and dataplane is called as a worker node.Ideally one master node is enough and we can have more worker nodes,if master node goes down all the worker nodes will not work.

### Control plane components:

Kube api-server: K8s API is the frontend of the kubernetes control plane and is how users interact with K8s cluster. It determines if a request is valid or not and then process it.

Kube scheduler: It schedules the pods on the wroker nodes based on the resource availability.
	
kube controller-manager: It is the non-terminating loop that regulates the state of the system. We have multiple controllers that are running on the cluster to ensure cluster desired state.

etcd:  etcd is a key-value store used to manage the critical information like configuration data, state data, and metadata for Kubernetes.

Cloud controller-manager(CCM): This component comes into picture when you use cloud provider managed kubernetes distribution (EKS, AKS,EKE). It will interact with cloud provider to get the things done.

### Data plane components:

Kubelet: The kubelet is the primary "node agent" that runs on each node. Itfacilitates communication between the control plane and data planes, allowing for the effective deployment and execution of containerized applications. It manages the life cycle of pod.

kubeproxy: It is the network proxy which maintains the network rules on nodes, updating ip tables.

container runtime: It is essential to run the containers, it's responsible for managing the execution and lifecycle of the containers within the Kubernetes environment.  






![](https://kubernetes.io/images/docs/kubernetes-cluster-architecture.svg)
