# Instructions for setting up Minikube with nginx Part 1

1. Start minikube

```bash
minikube start
```

2. Enable Ingress

```bash
minikube addons enable ingress
```

3. Set up ingress and apps

```bash
kubectl apply -f .
```

This may take more than once for configs to properly be active

4. Verify Pods are Running

```bash
kubectl get pods
```

5. Test the nginx load balancing using curl:

```bash
curl http://$(minikube ip)/
```

This may take more than once to see both outputs

# Removal

```bash
kubectl delete -f .
```
