# Kubernetes-Demo
Kubernetes runs containers in pods. It makes sure they stay up, restarts them if they crash, and can scale automatically.

Start Minikube to run Kubernetes locally, to observe cluseter behavior on local machine:
```
minikube start
```

Build inside Minikube's Docker:
```
eval $(minikube docker-env)
docker build -t demo-app .
```

Run the deployment:

```
kubectl apply -f deployment.yaml
```
Show that 2 pods are running.
```
kubectl get pods
```

Simulate a crash
```
kubectl delete pod <one-pod-name>
```

Kubernetes automatically spins up a new pod to replace it.
```
kubectl get pods
```

Access the app:
```
minikube service demo-service
```

To stop:
```
minikube stop
```

That’s Kubernetes in action — it keeps our app alive, balanced, and scalable without us having to manually restart anything.