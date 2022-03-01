# miniproject

### Clean up and start minikube
```bash
minikube start --alsologtostderr
```

### Add deployment and service manifests
```bash
kubectl apply -f frontend-deployment.yaml
kubectl apply -f frontend-service.yaml
kubectl apply -f redis-leader-deployment.yaml
kubectl apply -f redis-leader-service.yaml
kubectl apply -f redis-follower-deployment.yaml
kubectl apply -f redis-follower-service.yaml
```

### Set up port forward for localhost:8080
```bash
kubectl port-forward svc/frontend 8080:80
```

### Optional
```bash
minikube dashboard
```

### Should be able to open http://localhost:8080 and store keys in redis

[Guestbook demo]: https://kubernetes.io/docs/tutorials/stateless-application/guestbook/

### CLEANUP

<!-- EXTRA INFO
kubectl exec -it redis-leader-766465cd9c-vzkwc /bin/bash

kubectl create deployment redis6 --image=redis:6.2.6-bullseye
kubectl expose deployment redis6 --type=LoadBalancer --port=6379

kubectl create deployment nginx --image=nginx:1.16.1
kubectl expose deployment nginx --type=LoadBalancer --port=9001

https://kubernetes.io/docs/concepts/services-networking/service/
-->
