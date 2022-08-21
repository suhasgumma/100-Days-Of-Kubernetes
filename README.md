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


## Day 24 -- Ingress

### Ingress

Ingress Exposes multiple Services through a single cloud load-balancer.

### Ingress vs Load-balancer.png

<img src="Images For Readme/Ingress vs Load-balancer.png" height = 300 width = 500>

### Ingress Fanout

<img src="Images For Readme/Ingress Fanout.png" height = 300 width = 500>











