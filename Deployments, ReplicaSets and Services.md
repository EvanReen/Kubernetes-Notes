# Deployments, ReplicaSets and Services

These are all type of controllers. 

****Benefits of Controllers****
- Application reliability: where multiple instances of an application running, prevent problems if one or more instance fails.
- Scaling: when your pods experience a high volume of requests, kubernetes allows you to scale up your pods, allowing for a better user experience. 
- Load balancing: where having multiple versionsof a pod running allow traffic to flow to different pods, and doesnt overload a single pod or node

****Kinds of Controllers****
- ReplicaSets
- Deployments 
- DaemonSets
- Jobs
- Services

## ReplicaSets
Ensures that the specified number of replica for a pod are running at all times.

## Deployments
A deployment controller provides declarative updates for pods and ReplicaSets.

- This means you can describe the desired state of a deployment in a YAML file, and the deployment controller will align the actual state to match. 
- Manages a ReplicaSet.

- pod management: running a ReplicaSet allows you to deploy a number of pods, and check their status as a single unit.

- Pause and Resume: pause deployment, make changes, resume deployment. 

## DaemonSets
DaemonSets ensure that all nodes run a copy of a specific pod.

- As nodes are added and removed from the cluster, a DaemonSet will add or remove the required pods. 

## Jobs 
A supervisor process for pods carrying out batch jobs.

- Jobs are used to run indivual processes that run once and complete successfully. 

## Services
A service allows the communcation between one set of deployments with another. 

- use a service to get pods in two deployments to talk to each other. 

***Kinds of Services***
- Internal: IP is only reachable within the cluster 
- External: endpoint available through node IP: port (called NodePort)
- Load Balancer: Exposes application to the internet with a load balancer (available with a cloud provider)


