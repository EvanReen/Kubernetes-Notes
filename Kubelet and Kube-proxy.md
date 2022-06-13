# Kubelet + Kube-proxy 

## Kubelet 

The Kubelet is the "Kubernetes Node Agent" that runs on each node.

****Kubelet Roles****
- Communicates with API server to see if pods have been assigned to nodes.
- Executes the pod containers via a container engine.
- Mounts and runs pod volumes and secrets.
- Executes health checks to identify pods/node status. 

The Kubelet works in terms of podspec.
- Podspec: YAML file that describes a pod. 
-The kubelet takes a set of podspecs that are provided by the kube-apiserver and ensures that the containers described in those podspecs are running and healthy.
- Kubelet only manages containers that were created by the API server - not any containers running on the node. 

## Kube-proxy

The network proxy is called the Kube-proxy. This is another process that runs on all the worker nodes.
- It reflects the services as defined on each node, and can do simple network stream or round-robin forwarding across a set of backends. 

***Three modes of the Kube-proxy***

1: user space mode

2: IP tables mode

3: ipvs mode (alpha feature)

******Why these modes are important******
- Services defined against the API server: kube-proxy watches the API server for the addition of and removal of services. 
- for each new service, kube-proxy opens a randomly chosen port on the local node.
- Any connections to that chosen port are proxied to one of the corresponding back-end ports.
 
