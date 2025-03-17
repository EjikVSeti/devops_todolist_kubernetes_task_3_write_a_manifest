# Deployment Instructions for ToDo App in Kubernetes

## 1. Apply Kubernetes Manifests

```shell
kubectl apply -f .infrastructure/namespace.yml
kubectl apply -f .infrastructure/busybox.yml
kubectl apply -f .infrastructure/todoapp-service.yml
kubectl apply -f .infrastructure/todoapp-pod.yml
```

## 2. Verify Deployment Status

```shell
kubectl get pods -n todoapp
kubectl get services -n todoapp
```

## 3. Test Readiness & Liveness Probes

```shell
kubectl exec -it busybox -n todoapp -- curl http://todoapp:8000/api/readiness
kubectl exec -it busybox -n todoapp -- curl http://todoapp:8000/api/liveness
```

## Final step: 

Then open: http://localhost:30080/
