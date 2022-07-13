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





