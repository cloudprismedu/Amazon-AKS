# **Custom Resource Definitions(CRDs):**

- Custom Resource Definitions(CRDs) are a kubernetes feature that 
allows users to create their own custom resources.
- These custom resources extend the Kubernetes API and enable users to define and manage new types of objects beyond the built-in Kubernetes objects (like pods, services and deployments).

**Following are the key points about CDRs:**

1. **`Custom Resources:`** 

    -   A custom resource is an extension of the kubernetes API that enables users to store and retrive structured data

    -   Custom resources are often used to add custom objects that represent a domain-specific entity or to implement new application features.

2. **`Custom Resource Definitions:`**

    - CRDs are used to define the schema and behavior of custom resources.
    -   They tell Kubernetes about the new resource type, including its name, version and validation rules.
    - Once a CRD is applied to a cluster, Kubernetes starts to recognize and manage instances of the custom resource.

3. **`Declarative API:`**

    - CRDs allow users to declare the desired state of the custom resource in a manner similar to built-in kubernetes objects.
    - This declarative approach means users can manage the lifecycle of custom resources using the same tools and practices as for other Kubernetes resources.

4. **`Controller:`**

    -   TO make custom resources useful, users often implement a controller that watches for cahnges to instances of the customresource and takes action based on those changes.
    -   Controlles are typically implemented as custom Kubernetes controllers that extend the control plane.

5. **`YAML Definition:`**

    -   CRDs are defined using YAML files, which specify the details of the custom resource, such as its API version, kind, metadata and specification.
    -   The CRD YAML is then applied to the cluster using `kubectl`.
    
