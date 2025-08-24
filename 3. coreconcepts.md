# Kubernetes Core Concepts Notes

## 1. Pods

- **Definition:**  
  A Pod is the smallest deployable unit in Kubernetes. It can contain one or more containers (usually one). Containers inside a Pod share networking, storage, and namespace.

- **Lifecycle Phases of a Pod:**  
  - **Pending:** Pod is created but containers are not ready (e.g., pulling images).  
  - **Running:** At least one container is running or starting.  
  - **Succeeded:** All containers finished successfully.  
  - **Failed:** At least one container failed and won’t restart.  
  - **Unknown:** Kubernetes cannot determine Pod status.

- **Example:**  
  A web server running in a container is deployed inside a Pod. If the container crashes, Kubernetes will restart the Pod according to the defined policy.

***

## 2. ReplicaSets and Replication Controllers

- **ReplicaSet:** Ensures a specified number of Pod replicas run at any time. It maintains availability.  
- **Replication Controller:** Older version of ReplicaSet, mostly replaced by ReplicaSets.

- **Example:**  
  You want 3 copies of your web server Pod running for high availability. ReplicaSet ensures if one Pod dies, another is created automatically.

***

## 3. Deployments

- Used to declare the desired state of replicated Pods and perform **rolling updates and rollbacks**.

- **Example:**  
  You update your application version from 1.0 to 2.0. Deployment gradually replaces old Pods with new ones, avoiding downtime.

***

## 4. Services

Abstraction layer to expose Pods to other Pods or external traffic, providing stable networking.

- **Types of Services:**  
  - **ClusterIP:** Exposes service inside the cluster only (default).  
  - **NodePort:** Exposes service on each cluster node’s IP at a static port.  
  - **LoadBalancer:** Exposes service externally using a cloud provider’s load balancer.  
  - **ExternalName:** Maps service to an external DNS name.

- **Example:**  
  A frontend app uses a Service to communicate with the backend Pods. The Service load balances requests to healthy backend Pods.

***

## 5. Namespaces

- Virtual clusters inside a Kubernetes cluster for multi-tenancy and resource isolation.

- **Example:**  
  Dev, Test, and Prod environments run in different namespaces to separate resources and avoid conflicts.

***

## 6. Labels and Selectors

- Labels are key/value pairs attached to objects like Pods, used for organization and querying.  
- Selectors are used to find Pods matching certain labels.

- **Example:**  
  Label Pods with `app=frontend` and use selectors in Services to target those Pods.

***

## 7. ConfigMaps and Secrets

- **ConfigMaps:** Store non-sensitive configuration data separate from container images.  
- **Secrets:** Store sensitive data such as passwords, tokens, certificates.

- **Example:**  
  A database connection string is stored in a ConfigMap, while the database password is stored in a Secret. Pods read these at runtime for configuration.

***

