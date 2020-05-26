# Pod
- pods are smallest atomic item in k8s
- containers run in pods
    - usually a 1:1 relationship
    - if you go from 1 -> 2 containers running, it deploys a SECOND pod
- you can have multiple containers in pods
    - sometimes you can have helper containers in the same pod
    - you spin up multiple pods to scale, but can have multiple of different containers in a pod

### creating
```
    kubectl run nginx --image nginx
    pod name  ----^             ^---- whrere the image comes from
```
** NOTE looks like this syntax is deprecated, seems like `kubectl create` using json or yml is preferred 

### Using YML
4 required fields
- apiVersion
    - k8s api version (v1)
- kind
    - Pod, ReplicaSet, Deployment, Service
- metadata
    - stuff about the thing
        - name 
        - labels
    - format of a dictionary
    ex:
```
metadata:
    name: myapp-pod
    labels:
        app: myapp
        type: frontend
            <Can be whatever kv pair>
```
- spec
    - different for different objects
    - dictionary
    - for pod
    - containers is first value with a list of containres we need
```
spec:
    containers:
        - name: nginx-container
          image: nging

```