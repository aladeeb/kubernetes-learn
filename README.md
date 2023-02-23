# Kubernetes #
Kubernetes notes. 

## Architecture

- **Node**: the machine that will host the container runtime and the running containers.
- **Cluster**: group of nodes.
- **kubectl**: command line tool that interacts with the kube-apiserver and send commands to the master node.

### Master Components (Control Plane):
- etcd: key-value storage used to store k8s cluster data.
- kube-apiserver: centeral management entity that receives all REST requests. And the only components that comunicates with the etcd.
- kube-controller-manager: controls replications, services, pods and so on. Mainly controls the state of the objects.
- kube-scheduler: allocates the pods to run a node based on the node utilization 

### Node Components:
- kubelet: the main service in the node and it controls the state as per the kube-apiserver.
- kube-proxy: proxy service that runs on each node and responsible for the host subnetting and exposing the containers to the external world and perform request forwarding to the respctive containers/pods.

