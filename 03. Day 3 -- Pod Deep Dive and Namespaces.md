Day 3 -- Pod Deep Dive and Namespaces.

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
