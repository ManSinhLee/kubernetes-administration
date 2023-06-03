The architecture of Kubernetes consists of several key components that work together to manage containerized applications across a cluster of nodes. Here are the main architectural components of Kubernetes:

1. Master Node:
   - API Server: The API server is the central control plane component that exposes the Kubernetes API and acts as the primary interface for managing the cluster. It handles API requests, performs authentication and authorization, and validates and processes updates to the cluster's desired state.
   - etcd: etcd is a distributed key-value store used by Kubernetes to store and manage the cluster's configuration data, including the desired state of resources and runtime information.
   - Scheduler: The scheduler is responsible for assigning containers to nodes based on resource requirements, constraints, and various policies. It determines the optimal placement of pods within the cluster.
   - Controller Manager: The controller manager runs several controllers that monitor the state of the cluster and take actions to ensure the desired state is achieved. Examples of controllers include the replication controller, node controller, service controller, and endpoint controller.
   
2. Worker Nodes:
   - Kubelet: The kubelet is an agent that runs on each worker node and communicates with the master node. It manages and maintains the state of containers on the node, ensures they are running as expected, and reports their status back to the master.
   - Container Runtime: The container runtime, such as Docker or containerd, is responsible for running containers and managing their lifecycle on the worker nodes.
   - Kube-proxy: Kube-proxy is responsible for network proxying and load balancing within the cluster. It maintains network rules and routes to enable communication between services running on different nodes.
   
3. Networking:
   - Pod Networking: Each pod in Kubernetes gets its own unique IP address, allowing containers within the pod to communicate with each other directly.
   - Network Plugins: Kubernetes supports various network plugins, such as Calico, Flannel, and Cilium, which provide networking and network policy capabilities to manage communication between pods and external networks.

4. Add-ons:
   - DNS: Kubernetes includes a built-in DNS service that provides DNS-based service discovery for pods within the cluster.
   - Dashboard: The Kubernetes Dashboard is a web-based user interface that provides a graphical interface for managing and monitoring the cluster.
   - Ingress Controller: An Ingress controller provides external access to services within the cluster by managing ingress rules and configuring external load balancers or reverse proxies.
   - Logging and Monitoring: Kubernetes integrates with logging and monitoring solutions to capture and analyze logs and metrics from pods and nodes.

These components work together to create a distributed and scalable platform for managing containerized applications. The master node controls the cluster state, while worker nodes execute and manage containers. The networking layer enables communication between pods, and add-ons provide additional functionality for monitoring, logging, and external access.