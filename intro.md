# What are the Limitations in Docker?

- **Limited to Single Host:** Docker containers run on one machine only. It can’t manage containers spread across multiple servers by itself.
- **No Built-in Orchestration:** Docker alone does not handle scaling, load balancing, or automatic recovery of containers well. You need tools like Kubernetes for that.
- **Persistent Data Challenges:** Managing storage and persistent data in Docker containers is complex because containers are designed to be stateless and temporary.
- **Security Concerns:** Containers share the host OS kernel, which can sometimes lead to security risks if not properly isolated.
- **Networking Limitations:** Docker’s networking can get complicated when containers need to communicate over different hosts or complex network setups.

> **Remember for interview:** Docker is great for packaging and running apps, but it has challenges in scaling, orchestration, and persistent storage. Kubernetes solves many of these.

***

# Why is Kubernetes (K8s) Most Widely Used?

- **Container Orchestration:** K8s manages containers across many machines automatically — it handles deployment, scaling, and managing containerized apps.
- **Scalability:** Easily scale apps up or down depending on demand without manual intervention.
- **Self-Healing:** If a container or node fails, K8s automatically restarts or replaces it to keep the app running.
- **Load Balancing:** Distributes network traffic to keep apps responsive.
- **Multi-Cloud and Hybrid Support:** Works on various cloud providers and on-premises environments, making it flexible.
- **Strong Community & Ecosystem:** Huge community support and many tools/plugins are available.
- **Declarative Configuration:** Use YAML or JSON files to define the desired application state, making automation easier.

> **Remember for interview:** Kubernetes is popular because it solves container management at scale with automation, self-healing, and flexibility across clouds.


