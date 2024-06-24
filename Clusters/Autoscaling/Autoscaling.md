# **Autoscaling:**

- Autoscaling is a function that automatically scales our resources out and in to meet changing demands.
- This is a major Kubernetes function that would otherwise require extensive human resources to perform manually.

There are two type of Autoscaling:

    - Cluster Autoscaler
    - Application Autoscaling

### **Cluster Autoscaler:**

The kubernetes Cluster autoscaler automatically adjusts the number of nodes in our cluster when the pods fail or are rescheduled onto other nodes. The Cluster Autoscaler uses Auto Scaling groups.

-   **Purpose:** Adjusts the size of the Kubernetes cluster to meet the needs of your workloads.
- **Installlation:** Deploy via YAML manifest,
- **IAM Pemissions:** Needs specific permissions to interact with EC2 and Auto Scaling groups.

### **Application Autoscaling(Horizontal Pod Autoscaler(HPA)):**

-   **Purpose:** Automatically scales the number of pods in a deployment based on observes CPU utilization or other metrics/
- **Requirements:** Metrics Server must be deployed in the cluster to provide resource usage metrics.

### **Karpenter:**

- Karpenter is a flexible, high performance Kubernetes cluster autoscaler that helps improve application availability and cluster efficiency.
-   Karpenter launches right-sized compute resource in response to changing application load in under a minute.
- Through integrating Kubernetes with AWS, Karpenter can provision just-in-time compute resources that precisely meet the requirements of your workload.
- Karpenter automatically provisions new compute resources based on the specific requirements of cluster workloads.
- These include compte, storage, acceleration, and scheduling requirements.
- Amazon EKS supports clusters using Karpenter, although Karpenter works with any conformant Kubernete cluster.

