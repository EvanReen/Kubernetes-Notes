# Nodes + Pods

### Node
A node serves as a worker machine on a Kubernetes Cluster
- The node can be a physical computer or a virtual machine (vm)

******Node Requirements******
- A kubelet running
- container tooling like docker
- A kube-proxy process running 
- supervisord 

### Pod
A pod is the simplest unit you can interact with.
- it can create, deploy and delete pods and it represents one running process on your cluster.
- it represents one single unit of deployment. 

******Whats in the pod?******
- your docker application container
- storage resource
- unique network IP
- options that govern how the containers should run 

******Pod States******
- Pending: means the pod has been accepted by the Kubernetes system, but a container has not been created yet.
- Running: where a pod has been scheduled on a node + all of its containers are created and atleast one container is in a running state.
- Succeeded: all of the containers in the pod have exited with an exit stat of zero, which indicates successful execution. 
- failed: containers have failed + returned a non-zero exit status.
- CrashLoopBackOff: This is where a container fails to start + then kubernetes tries over and over again to try restart the pod. 
