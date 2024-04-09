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

4. Test the nginx load balancing using curl:

```bash
curl http://$(minikube ip)/
```
