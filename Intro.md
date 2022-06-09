# Kubernetes-Notes

Kubernetes is an open-source platform designed to automate deploying, scaling and operating application containers.

It's goal is to foster an ecosystem of components and tools that relieve the burden of running applications in public and private clouds.

There is a number of terms you will need to know before you dive into Kubernetes. 

## Containers and Containerization

- A container is a collection of software processes unified by one namespace, with access to an operating system kernel that it shares with other containers + little to no access between containers.

- Containerization is an approach of running applications on an OS (Operating System) such that the application is isolated from the rest of the system. 

### Difference between a container and a virtual machine (VM)
  ##### Container                                                                  
  - includes the application + all of its dependencies                         
  - shares the Kernel with other Containers
  ##### Virtual Machine (VM)  
  - includes one or many applications
  - The neccesary binaries + dependencies
  - The entire guest operating system to interact with the applications
                                                                                
## Architecture of Kubernetes Cluster 

![image](https://user-images.githubusercontent.com/74310324/172833432-9418974f-d2db-444f-9e92-69a8fc28df3d.png)

###### Master Node
- Responsible for the overall management of the Kubernetes Cluster. It has three components that take of communication, scheduling and Controllers.
###### API server
- allows you to interact with the Kubernetes API.
###### Schedular
- watched created pods, who do not have a Node design yet, and designs the pod to run on a specific node.
###### Controller Manager
- runs controllers. These are background threads that run tasks in a cluster.
###### etcd
- a simple distributed key value store. Kubernetes uses etcd as its database + stores all cluster data here.
###### kubectl
- command line interface for kubernetes. 
###### Work node
- where your applications operate
- They communicate back with the master node.
###### Kubelet
- an agent that communicates with the API server to see if pods have been assigned to the nodes.
- executes pod containers via the container engine.
- aware of pod and node states. 
- responds back to the master.
###### Kube-proxy 
- a network proxy and load balancer for the service, on a single worker node.
- it handles the network routing for TCP and UDP packets and performs connection forwarding.
###### Docker 
- works together with Kubelet to run containers on the node.
- containers of an application are tightly coupled together in a pod. 
- kubelet process communciates with the pods to check on state and health.
- The kube-proxy routes any packetst the pods from other resources that might be wanting to communicate with them. 
