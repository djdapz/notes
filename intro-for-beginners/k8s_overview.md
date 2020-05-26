## Architecture
#### Nodes
  - used to be called minions
  - Actual machine that k8s is installed on
    - Physical or virtual

#### Cluster
  - collection of multiple nodes
  
#### Master
  - Specially configured node
  - Watches over other nodes in cluster
  - Responsible for container orchestration
  
### Components
  - API Server = Frontend for kubernetes - endpoints for k8s
  - etcd = distributed key-value store - stores all config across all nodes
  - Scheduler = distributes work across nodes
  - controller = brain behind orchestration 
    - Notice and respond to things going down
  - container runtime
    - Docker in our time
  - kubelet
    - agent running on nodes
    - ensures everything is running as expected

#### master vs worker
  - Master
    - kube-apiserver (talks to kubelet)
    - etcd
    - controller
    - scheduler
  - Worker
    - container runtime
    - kubelet
    
## Kubectl (cube control)
  - `kubectl run hello-minikube`
    - deploys an app on the cluster
  - `kubectl cluster-info`
    - info about the cluster
  - `kubectl get nodes`
    - info about the nodes