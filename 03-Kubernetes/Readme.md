## Assessment Questions and Answers

### 1. What are the different types of services?

**Ans**:
There are three types of services present Kubernetes and they are as follow:

1. **ClusterIP**: This is the default service type. It assigns a virtual IP address to the service, which can only be accessed from within the K8 cluster.
2. **NodePort**: This service type exposes the service on a static port on each node in the cluster. This makes the service accessible from outside the cluster.
3. **LoadBalancer**: This service type uses a cloud provider's load balancer to expose the service to the internet. This is the most scalable and reliable service type.
 
### 2. What is a pod? 

**Ans**: 
A pod is the smallest unit of deployment present in Kubernetes. It is a group of one or more containers that are deployed together on a single node. 
Pods are ephemeral, meaning that they are created and destroyed as needed.

### 3. Create a pod with the above created custom image when a pod dies k8s should automatically restart

**Ans**:
```yaml
apiVersion: v1
kind: Pod
metadata:
  name: web-game-pod
spec:
  restartPolicy: Always
  containers:
  - name: web-game
    image: yashpimple22/web-game:latest
    ports:
    - containerPort: 3001
```
The above manifest will create a pod named *web-game-pod* with a single container named *web-game*. The container will run the *yashpimple22/web-game:latest* image and 
will listen on port **3001** additionally **restartPolicy: Always** will always tell Kubernetes to restart the container if it dies.

### 4. How to access the custom application with a specific port?

**Ans**:
To access our custom application running on port 3001, we need to use the following command:

```bash
kubectl get pods
```
This command will list all of the pods present in the cluster. Once you have identified the **pod ID** of your pod, you can use the following command to access the application:

```bash
kubectl port-forward <pod-id> 3001:3001
```
This above command will forward port **3001** on the pod to port **3001** on your local machine. You can then access the application at **http://localhost:3001**.

![Pod](https://github.com/YashPimple/DevOps-Internship-Assesment/assets/97302447/90e7ce17-0072-40d2-9b7a-b94ad883a6a8)
