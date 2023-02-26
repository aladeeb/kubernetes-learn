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

---

## Concepts
- **Pod**: it's the smallest object in k8s and it contains the container or multiple containers conncet together throgh the same network namespace and the same storage.
- **Service**: 
- **Volume**: 
- **Namespace**: 
- **Deployment**: 


---

## Pods
### Commands:
- `kubectl get pods`: retreives the pods and its details.
  - `-o wide`: shows the IP and more details about the node that runs the pod.
- `kubectl describe pod POD_NAME`: retreives the pod details like containers inside it, network or events.
- `kubectl run POD_NAME --image=IMAGE_NAME`: runs a pod with a specific name and specific image.
  - `--dry-run=client -o=yaml`: output the pod yaml
- `kubectl create -f FILE_NAME.yml`: creates a pod from yml file.
- `kubectl apply -f FILE_NAME.yml`: apply changes on a pod from yml file.


---

## ReplicaSet
### Commands:
- `kubectl get replicaset`: get all replicasets.
- `kubectl delete replicaset REPLICASET_NAME`: delete specific replicaset.
- `kubectl replace -f FILE_NAME.yml`: updates the existing replicaset.
- `kubectl scale -f FILE_NAME.yml --replicas=NUM_OF_REPLICAS`: increase/decrease the replicas to NUM_OF_REPLICAS.
- `kubectl scale replicaset REPLICA_NAME --replicas=NUM_OF_REPLICAS`: increase/decrease the replicas to NUM_OF_REPLICAS.

---

## Deployment
### Commands:
- `kubectl get deployment`: get all deployments.
- `kubectl delete deployment DEPLOYMENT_NAME`: delete specific deployment.
- `kubectl replace -f FILE_NAME.yml`: updates the existing deployment.

---
## Controllers
- ReplicationController
- ReplicaSet
- Deployment
---


```
kubectl run hello-minikube
kubectl cluster-info
kubectl get all
kubectl get nodes
kubectl run redis --image=redis --dry-run=client -o yaml
```