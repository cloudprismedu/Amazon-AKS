# **Kubernetes Components:**

-   A Kubernets Cluster consists of a set of worker machines, called nodes, that run containerized applications.
- Each cluster has at least one worker node.
- The worker node(s) host the Pods that are the components of the application workload.
-   the control plane manages the worker nodes and the pods in the cluster.
-   In production enviornments, the control plane usuapply runs across multiple computers and a cluster usually runs multiple nodes, providing fault-tolearnce and high availability.

### **Control Plane Components:**
----------------------------------

The control plane's components make global decisions about the cluster, as well as detecting and responding to cluster events.

Control Plan components can be run on any machine in the cluster. However, for simplicity, setup scripts typically start all control plane components on the same machine, and do not run user containers on this machine.

#### **`kube-apiserver`:**

-   The API server is a component of the kubernetes control plane that exposes the Kubernetes API. The API server is the front end for the Kubernetes control plane.

- The main implementation of a kubernetes API server is kube-apiserver. kube-apiserver is designed to scle horizontally-that is, it scales by deploying more instances. you can run several instances of kube-apiserver and balance traffic between those instances.

#### **`etcd:`**

- Consistent and highly-available key value store used as Kubernetes' backing store for all cluster data.
-   All cluster states and configurations are stored here.

#### **`kube-scheduler:`**

-   Responsible for scheduling pods to nodes based on various factors like resource requirements, policy constraints, affinity/anti-affinity specifications, data locality, etc..

#### **`kube-controller-manager:`**

-   Runs controllers that regulate the state of the cluster, such as the Node Controller, Replication COntrollers, Endpoints Controller and others. 
-   Each controller watches the shared state of the cluster through the API server and makes changes to move the current state towards the desired state.

#### **`Cloud-Controller-Manager:`**

- A Kubernetes control plane component that embeds cloud-specific contol logic.
- The cloud controller manager lets link cluster into cloud provider's API, and separates out the components that interact with that cloud platform from components that only interact with cluster.
-   It manages cloud-specific components such as node instances, networking and storage.
-   The cloud-controller-manager only runs controllers that are specific to cloud provider.
-   If we are running Kubernetes on our own premises, or in a learning environment inside our own PC, the cluster does not have a cloud controller manager.
-   As with the kube-controller-manager, the cloud-controller-manager combines several logically independent control loops into a single binary that you run as a single process.
-   You can scale horizontally (run more than one copy) to improve performance or to help tolerate failures.

Following controllers can have cloud provider dependencies:

**Node Controller:** For checking the cloud provider to determine if a node has been deleted in the cloud after it stops responding.

**Route Controler:** For setting up routes in the underlying cloud infrastructure.

**Service Controller:** For creating, updating and deleteing cloud provider load balancers.



### **Node Components:**
-------------------------

#### **`kubelet:`**

-   An agent that runs on each node in the cluster.
-   It ensures that containers are running in a Pod, maintains the Pod's lufecycle, and reports node and pod status to the control plane.

#### **`kube-proxy:`**

-   A network proxy that runs on each node.
-   It maintains network rules to allow network communciation to your pods from network sessions inside or outside of cluster.
-   kube-proxy uses the operating system packet filtering layer if there is one and otherwise forwards the traffic itself.

#### **`Container Runtime:`**

-   The software responsible for running containers.
-   Kubernetes supports several runtimes, including Docker, containered and CRI-O

### **Additional Components:**
------------------------------

#### **`kubectl:`**

-   A command-line tool used to interact with the Kubernetes API server.
-   It Allows administrators to deply applications, inspect and manage cluster resources, and view logs.

#### **`coredns:`**

-   A DNS server used by Kubernetes to provide service discovery within the cluster.
-   It resolved DNS names for services, enabling inter-service communication.

