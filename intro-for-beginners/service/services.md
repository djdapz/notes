# Services

##  Types of Services

### Node Port & Load Balancer
- Makes internal pod accessible on port on the node

There are 3 ports involved
1) Target Port: Port on the container that you want to access
2) Port: On the service itself. 
    - Also has an IP address (called the cluster IP of the service)
3) NodePort: actual port we use to access from ouside of the node
    - Can be from 30000 - 32797
 
```yaml
apiVersion: v1
kind: Service
metadata: 
    name: myapp-service
spec: 
    type: NodePort  
    ports:
      - targetPort: 80
        port: 80
        nodePort: 30008
    selector:
      app: myapp
      type: front-end
```
 
This can work as a LoadBalancer if the selector matches multiple apps!
It even works across nodes!!!

### Cluster IP
- Creates a virtual IP inside the cluster to enable ocmmunication between different services.
- For cluster:cluster networking

```yaml

apiVersion: v1
kind: Service
metadata:
    name: back-end
spec:
    type: ClusterIP
    ports:
     - targetPort: 90
       port: 80
    selector:
      app: myapp
      type: back-end

```
