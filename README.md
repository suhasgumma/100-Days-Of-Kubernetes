# 100 Days Of Kubernetes

## Day 1 & 2

### Concepts Covered:
✨ Introduction to Kubernetes.

✨ Kubernetes as the Operating System of the Cloud.

✨ K8s cluster Architecture Deep Dive.

✨ Declarative Model & Desired State.

✨ Intro to Pods, Deployments & Service Objects.

✨ Kubectl

✨ Hands-on with "https://labs.play-with-k8s.com/"


### Commands

#### Initialize Cluster Master Node In Kubernetes Playground
```
kubeadm init --apiserver-advertise-address $(hostname -i) --pod-network-cidr 10.5.0.0/16 
```

#### Initialize cluster networking In Kubernetes Playground

```
kubectl apply -f https://raw.githubusercontent.com/cloudnativelabs/kube-router/master/daemonset/kubeadm-kuberouter.yaml
```

### See the Nodes in Cluster

```
kubectl get nodes
```

## Day 3 -- Pod Deep Dive and Namespaces.

✨ Why Pods

✨ Static Pods vs controllers

✨ Single-container and multi-container Pods

✨ Deploying Pods

✨ Anotomy of Pods

✨ Hands-on with Pods

✨ Namespaces in K8s

### Commands Explored

```
kubectl explore pods --recursive
kubectl apply -f pod.yml
kubectl get pods
kubectl describe
kubectl logs
kubectl get namespaces
kubectl create ns newNamespace
kubectl config set-context --current --namespace newNamespace
kubectl config set-context --current --namespace default
kubectl delete ns newNamespace
```

## Day 4 -- Services, Service Discovery & Volumes

✨ Introduction to Kubernetes Services

✨ EndPoint Objects

✨ Accessing Services from inside the Cluster

✨ Accessing Services from outside the Cluster

✨ Service Registration & Service Discovery.

✨ Kubernetes Volumes

✨ EmptyDir and hostpath


## Day 5 -- Volumes, ConfigMaps and Secrets

✨ Persistent Volumes (PVs).

✨ Persistent Volume Claims (PVCs).

✨ Storage Classes.

✨ ConfigMaps and need for ConfigMaps

✨ Secrets

✨ Injecting configMaps and Secrets into Containers during runtime.


## Day 6 -- StatefulSets to Threat Modelling Kubernetes

✨ StatefulSets in Kubernetes

✨ The Kubernetes API Deep Dive

✨ API Security - AuthN, AuthZ and Admission Control

✨ RBAC

✨ Threat Modelling Kubernetes


```
StatefulSets handle Pods much more delicately than Deployments.
```

```
API Server runs as a set of Pods on kube-system Namespace on Control Plane Nodes because it is a Control Plane Service.
```

```
RESTful API --> Modern Web API dealing with CRUD-style requests with HTTP.
```

```
Role Based Access Control Model (RBAC):

Which USER can perform which ACTIONS against which RESOURCES.

```

## Day 7-12

Setting up a Personal Project in Collaboration with @jaideep99 and @navaneethnanda

Link to the Project - https://github.com/suhasgumma/CricRadio-Containerizing-using-Docker

## Day 13-17

Kubernetizing the CricRadio Project

Link to Kubernetes Manifest Files and Architecture - https://github.com/suhasgumma/CricRadio-Kubernetes

## Day 18-19

The Why of Kubernetes Design


## Day 20

Kubernetes 101 Workshop by Saiyam Pathak

Youtube Link: https://www.youtube.com/watch?v=PN3VqbZqmD8

## Day 21

Containers & Kubernetes Security Workshop by Rewanth Tammana

Youtube Link: https://www.youtube.com/watch?v=ka0C09CAfho&t=8089s

## Day 22

"GitOps with ArgoCD" Workshop by CodeFresh's Dan.

Youtube Link: https://www.youtube.com/watch?v=5rwIIusbUWM

## Day 23 -- Helm & Datree
### Fundamentals Of Helm

#### What is Helm?

Package Manager for Kubernetes. Primary Feature is packaging YAML files & distributing them in Public & Private repositories. Second feature is Templating engine.

#### What are Helm Charts?

Bundle of YAML files.

#### Helm Chart Structure
```
chartName/
  chart.yaml    //chart's metadata
  values.yaml   // Substitutes in template files
  charts/       // Chart Dependencies
  templates/
```

### Introduction to Datree

#### Problem Datree is Solving --> Preventing Kubernetes Misconfigurations from reaching Production. 

#### Does that through a series of checks
✨ YAML Validation.

✨ Kubernetes Schema Validation 

✨ Policy Check (Check the policies selected beforehand from available polocies. Currently there are 60 polocies)

### Datree policies
<img src="Images For Readme/Datree Policies.png" height = 300 width = 500>

### Kubernetes Schema Validation Fail
<img src="Images For Readme/Kubernetes Schema Validation Fail.png" height = 300 width = 500>

### Policy Check Fail
<img src="Images For Readme/Policy Check Fail.png" height = 300 width = 500>


## Day 24 -- Ingress, Metrics Server & Horizantol Pod Auto Scaling

### Ingress

Ingress Exposes multiple Services through a single cloud load-balancer.

### Ingress vs Load-balancer.png

<img src="Images For Readme/Ingress vs Load-balancer.png" height = 300 width = 500>

### Ingress Fanout

<img src="Images For Readme/Ingress Fanout.png" height = 300 width = 500>

### __________________________________________________________________________________________________________________________________________________________________________________________

### Metrics Server

#### Collects resource metrics from kubelets & exposes them in K8s API server through metrics API for use by HPA & VPA

### __________________________________________________________________________________________________________________________________________________________________________________________

### Horizontal Pod Auto Scaling

HorizantolPodAutoScaler **automatically** updates workload resources to match demand.

```
Horizantol Scaling --> Deploy more Pods.
Vertical Scaling --> Assign more resources (CPU, memory, etc) to existing pods.
```

### HPA Controller 

Adjusts the desired scale of the workloads to match observed metrics (average CPU utilization, etc)

```
desiredReplicas = ceil[currentReplicas * (currentMetricValue / desiredMetricValue)]
```

## Day 25 -- KubeCost & StatefulSets

### KubeCost
Monitor & Reduce Kubernetes Spend
#### Refer to Kubecost video by Kunal:
https://www.youtube.com/watch?v=GYgFWJmnpHk

### StatefulSets
Workload API object designed for stateful applications

#### Refer to StatefulSets Video of Nana:
https://www.youtube.com/watch?v=pPQKAR1pA9U

#### Kubernetes Docs StatefulSets
https://kubernetes.io/docs/concepts/workloads/controllers/statefulset/

#### Run a Replicated Stateful Application Demo
* https://kubernetes.io/docs/tasks/run-application/run-replicated-stateful-application/

#### Scale a StatefulSet Demo
* https://kubernetes.io/docs/tasks/run-application/scale-stateful-set/


## Day 26 -- Role Based Access Control (RBAC)
✨ Service Accounts
  * Processes in Containers and other third party applications could also contact the api-server.
    They are authenticated as a particular Service Account.
  
✨ Role
  * Sets Permission within a Namespace
  
✨ Cluster Role
  * Sets Permission across the cluster

✨ RoleBinding & ClusterRoleBinding
  * rolebindings grant the permissions defined in Role/ClusterRole to a user or a set of users. 
  
Documentation is informative & clear. Link to the documentation:
https://kubernetes.io/docs/reference/access-authn-authz/rbac/

## Day 27 -- Kubernetes Security Best Practices and Introduction to kubescape
### Kubernetes Security Best Practices
#### Number One Issue: 
Attacker Getting Access from the Kubernetes Platform to the underlying Operating System.

#### Security Mechanisms should be redundant. There should be multiple mechanisms at multiple levels.

### Resources
* Kubernetes Security Best Practices Video of Nana:
  https://www.youtube.com/watch?v=oBf5lrmquYI
  
* Kubernetes Hardening Guide: Cybersecurity Technical Report by NSA & CISA

* Hacking and Hardening Kubernetes Clusters- CNCF video:
  https://www.youtube.com/watch?v=vTgQLzeBfRU&t=730s
 
* Hacking into Kubernetes Security for Beginners- CNCF video:
  https://www.youtube.com/watch?v=mLsCm9GVIQg&t=244s

* Kubernetes Security Best Practices: Definitive Guide by Jonathan Kaftzan of Armo: 
  https://www.armosec.io/blog/kubernetes-security-best-practices/
  
### Best Practices from Nana's Video:

#### Best Practice 1: Scan Images & Scan them regularly.

#### Best Practice 2: Run as non-root

#### Best Practice 3: Users & Permissions with RBAC.

#### Best Practice 4: Define Communication rules between Pods by using Network polocies.

#### Best Practice 5: Encrypt cluster Internal Communication.

#### Best Practice 6: Secure Secret objects by encrypting them. 

#### Best Practice 7: Secure etcd store

#### Best Practice 8: Automated Backup & Restore.

#### Best Practice 9: Configure Security Polocies

#### Best Practice 10: Have a proper strategy & mechanism for disaster recovery. 



