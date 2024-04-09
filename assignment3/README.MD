# Instructions for setting up Minikube with nginx and backend apps

1. Start minikube

```bash
minikube start
```

## Deploying nginx with ConfigMap

1. Apply the ConfigMap and Deployment for nginx:

```bash
kubectl apply -f nginx-configmap.yaml
kubectl apply -f nginx-dep.yaml
```

2. Expose the nginx service:

```bash
kubectl apply -f nginx-svc.yaml
```

3. Verify the nginx deployment:

```bash
kubectl get pods -l app=nginx
```

4. Verify Nginx Service:

```bash
kubectl get svc nginx-svc
```

## Setting up Ingress for nginx

1. Apply the Ingress configuration for nginx:

```bash
kubectl apply -f nginx-ingress.yaml
```

2. Enable Ingress

```bash
minikube addons enable ingress
```

3. Test the nginx load balancing using curl:

```bash
curl http://$(minikube ip)/
```

## Deploying backend apps

1. Apply the Deployments and Services for app-1 and app-2:

```bash
kubectl apply -f app-1-dep.yaml
kubectl apply -f app-1-svc.yaml
kubectl apply -f app-2-dep.yaml
kubectl apply -f app-2-svc.yaml
```

2. Verify the deployments:

```bash
kubectl get pods -l app=app-1
kubectl get pods -l app=app-2
```
