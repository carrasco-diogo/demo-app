# Pre requirements
 - Docker 
 - minikube


# Getting started

Create a Secret for the postgres sql password: 

```
kubectl create secret generic db-credentials \
  --from-literal=username=<o-teu-username> \
  --from-literal=password=<a-tua-password>
```

## Create the DB service: 
```
minikube kubectl -- apply -f k8s/postgres.yaml
```

## Making it accessible:

```
minikube kubectl -- apply -f k8s/service.yaml
```

## Deploy the app inside a kubernetes cluster:

```
minikube kubectl -- apply -f k8s/deployment.yaml
```