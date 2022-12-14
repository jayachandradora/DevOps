# DevOps
Learn DevOps 

## Concepts
A.	Kubernetes is the concept of container deployment. Kubernetes is a tool used to manage clusters of containerized applications. In computing, this process is often referred to as orchestration. <br>
B.	A developer can then use the Kubernetes API to deploy, scale, and manage containerized applications.<br>
C.	K8s automatically orchestrates scaling and failovers for your applications and provides deployment patterns.<br>
D.	It ensures there is no downtime in a production environment. For example, if a container goes down, another automatically takes its place without the end-user ever noticing.<br>
E.	Kubernetes is not only an orchestration system. It is a set of independent, interconnected control processes. Its role is to continuously work on the current state and move the processes in the desired direction.<br>

## Features

![image](https://user-images.githubusercontent.com/115500959/196356431-c4a497be-e6a2-49ee-95ba-f64197413e95.png)

## Architecture
![image](https://user-images.githubusercontent.com/115500959/196356251-34c07fac-0579-4712-91c5-1817df18f526.png)
![image](https://user-images.githubusercontent.com/115500959/196356313-a04a6830-ba1a-4652-ac75-ddf9a5962bdb.png)
![image](https://user-images.githubusercontent.com/115500959/196356347-772d270b-666f-4210-b735-7ad3a1235c5e.png)
![image](https://user-images.githubusercontent.com/115500959/196356487-e581fd39-f967-400b-9511-640ead9406b9.png)


### Master Node: <br>
**API Server:** The API Server is the front-end of the control plane and the only component in the control plane that we interact with directly. Internal system components, as well as external user components, all communicate via the same API.<br><br>
**Key-Value Store (etcd):** The Key-Value Store, also called etcd, is a database Kubernetes uses to back-up all cluster data. It stores the entire configuration and state of the cluster. The Master node queries etcd to retrieve parameters for the state of the nodes, pods, and containers.<br><br>
**Controller:** The role of the Controller is to obtain the desired state from the API Server. It checks the current state of the nodes it is tasked to control, and determines if there are any differences, and resolves them, if any.<br><br>
**Scheduler:**  A Scheduler watches for new requests coming from the API Server and assigns them to healthy nodes. It ranks the quality of the nodes and deploys pods to the best-suited node. If there are no suitable nodes, the pods are put in a pending state until such a node appears.<br><br>
**Worker Node:**
Worker nodes listen to the API Server for new work assignments; they execute the work assignments and then report the results back to the Kubernetes Master node.<br><br>
**Kubelet:** The kubelet runs on every node in the cluster. It is the principal Kubernetes agent. By installing kubelet, the node???s CPU, RAM, and storage become part of the broader cluster. It watches for tasks sent from the API Server, executes the task, and reports back to the Master. It also monitors pods and reports back to the control panel if a pod is not fully functional. Based on that information, the Master can then decide how to allocate tasks and resources to reach the desired state.<br><br>
**Container Runtime:** The container runtime pulls images from a container image registry and starts and stops containers. A 3rd party software or plugin, such as Docker, usually performs this function.<br><br>
**Kube-proxy:** The kube-proxy makes sure that each node gets its IP address, implements local iptables and rules to handle routing and traffic load-balancing.<br><br>
**POD:** A pod is the smallest element of scheduling in Kubernetes. Without it, a container cannot be part of a cluster. If you need to scale your app, you can only do so by adding or removing pods. The pod serves as a ???wrapper??? for a single container with the application code. Based on the availability of resources, the Master schedules the pod on a specific node and coordinates with the container runtime to launch the container. In instances where pods unexpectedly fail to perform their tasks, Kubernetes does not attempt to fix them. Instead, it creates and starts a new pod in its place. This new pod is a replica, except for the DNS and IP address. This feature has had a profound impact on how developers design applications.<br>
**Kubernetes Service:**<br><br>
Pods are not constant. One of the best features Kubernetes offers is that non-functioning pods get replaced by new ones automatically. Services are introduced to provide reliable networking by bringing stable IP addresses and DNS names to the unstable world of pods.<br><br>

## Helm Chart 

![image](https://user-images.githubusercontent.com/115500959/196358738-a7a096f1-845b-483e-8cda-bf85cffeaede.png)

![image](https://user-images.githubusercontent.com/115500959/198503154-e4fc6a0a-f8fd-4253-a19a-8d44b23e1359.png)

## Docker Components
Learn about Docker Engine and its Components
The first approach for you to understand the docker architecture is by gaining insight into the Docker Engine concept. 
It has components that are responsible for making the entire system work. Docker Engine is behind the service aspects of
developing, assembling, shipping and running the applications. 

The components that are being used within Docker Engine are as follows:

### 1. Docker Daemon
```
It is more like a background process that intends to manage the docker containers, images, storage,  volumes, and networks.
The job of the Docker daemon is to keep track of the API requests that are proposed upon it and process them without interruptions.
```
### 2. Docker Engine REST API
```
As the name suggests, it is the specific API that the applications use for interacting or communicating with Docker daemon. 
An HTTP client has accessibility to REST API. In precise, this API gives instructions to the Docker daemon on what it should do 
within the engine and architecture.  
````
### 3. Docker CLI
```
Command Line Interface is more of a client that interacts with docker daemon. It is quite useful in terms of entering or 
accessing the docker commands. Docker CLI simplifies the way you manage the instances of your container. The seamlessness of
managing the container instances makes it easy for the developers to carry out their work process. 
```
![image](https://user-images.githubusercontent.com/115500959/198503641-b2cfdef6-6f3d-40c0-b030-b7862f55fdd7.png)

