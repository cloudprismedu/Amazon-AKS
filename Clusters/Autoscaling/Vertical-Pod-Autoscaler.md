# **Vertical Pod Autoscaler:**

- The Kubernetes Vertical Pod Autoscaler automatically adjusts the CPU and memory reservations for our pods to help "right size" our applications
- This adjustment can improve cluster resource utilization and free up CPU and memory for other pods.
- Autoscaling is configured with a `Custom Resource Definition Object` called `VeriticalPodAutoscaler`.
- It Allows to specify which pods should be vertically autoscaled as well as if/how the resource recommendations are applied.

**There are four modes in which VPAs Operate:**

- **`Auto`:** 

    - VPA assigns resource requests on pod creation as well as updates them on existing pods using the preferred update mechanism. 
    - Currently, this is equivalent to "Recreate" (see below). Once restart free ("in-place") update of pod requests is available, it may be used as the preferred update mechanism by the "Auto" mode.

- **`Recreate`:** 

    - VPA assigns resource requests on pod creation as well as updates them on existing pods by evicting them when the requested resources differ significantly from the new recommendation (respecting the Pod Disruption Budget, if defined). 
    - This mode should be used rarely, only if you need to ensure that the pods are restarted whenever the resource request changes. 
    - Otherwise, prefer the "Auto" mode which may take advantage of restart-free updates once they are available.

- **`Initial`:**

    - VPA only assigns resource requests on Pod creation and never changes them later.

- **`Off`:**

    - VPA does not automatically change the resource requirements of the pods.
    - The recommendations are calulated and can be inspected in the VPA object.
