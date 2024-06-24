# **Workloads:**

In Kubernetes, workloads refer to applications running on the cluster. Different workload types cater to various application needs and deployment strategies.

- **`Pods`:**

    - The smallest and simplest Kubernetes Object. A Pods represents a single instance of a running process in our cluster and can contain one or more containers.

- **`ReplicaSets`:**

    -   Ensures that a specified number of Pod replicas are running at any given time. It can be used to maintain a stable set of Pod replicase running, even during upgrades.

- **`Deployments:`**
    - Manages ReplicaSets and provides declaratives updates to applications. It enables rolling updates, rollbacks and scaling of applications.

- **`StatefulSets`:**

    - Manages the deployment and scaling of a set of Pods and provides guarantees about the ordering and uniqueness of these pods. It is used for stateful applications, such as databases, which require persistent storage.

- **`DaemonSets`:**

    -   Ensures that a copy of a pods run on all (or some) nodes in the cluster. It is commonly used for running background tasks like logging and monitoring.

- **`Jobs`:**

    - Creates one or more Pods and ensures that a specified number of them successfully terminate. Jobs are used for finite tasks, like batch processing.

- **`CronJobs`:**

    - Manages time-based jobs, which are similar to Unix cron jobs. They run jobs on a scheduled basis.

- **`ReplicationControllers`:**

    - An older form of ReplicaSets. It ensures that a specified number of pod replicas are running at any given time. It has been mostly replaced by ReplicaSets and Deployments.
    
