# Kubernetes-Demo
Kubernetes runs containers in pods. It makes sure they stay up, restarts them if they crash, and can scale automatically. This short tutorial will show you the power of Kubernetes in action.

## Prerequisites

1. Set up [minikube](https://minikube.sigs.k8s.io/docs/start/?arch=%2Fwindows%2Fx86-64%2Fstable%2F.exe+download) for local clusters.

2. Set up [kubectl](https://kubernetes.io/docs/tasks/tools/) to run command-line commands against Kubernetes clusters.
## Tutorial
1. Start Minikube to run Kubernetes locally.
```
minikube start
```

2. Build the demo app inside Minikube's Docker.
```
eval $(minikube docker-env)
docker build -t demo-app .
```
3. Run the deployment.
```
kubectl apply -f deployment.yaml
```
4. Notice that 2 pods are running.
```
kubectl get pods
```
5. Simulate a crash.
```
kubectl delete pod <one-pod-name>
```
Kubernetes automatically spins up a new pod to replace it.

6. Check and see that that 2 pods are still running
```
kubectl get pods
```
7. Access the app.
```
minikube service demo-service
```
8. Stop app.
```
minikube stop
```

That’s Kubernetes in action — it keeps our app alive, balanced, and scalable without us having to manually restart anything.

Reference for more basic minikube controls: https://minikube.sigs.k8s.io/docs/handbook/controls/
