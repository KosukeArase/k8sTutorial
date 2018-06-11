# Kubernetes Tutorial
Followed [this tutorial](https://inside.dmm.com/entry/2018/04/13/hello-kubernetes)

## Start cluster
```
$ minikube start
```

## Dashboard
Deploy dashboard
```
$ kubectl create -f kubernetes-dashboard.yaml
```

Connect dashboard via proxy
```
$ kubectl proxy
```

## Create objects
Create pod
```
$ kubectl create -f pod.yaml
```

Create deployment
```
$ kubectl run example-app-deploy -l phase=DEV --replicas=3 --image=nginx:1.7.9 --port=80
```

Create service
```
$ kubectl expose deployments/example-app-deploy
```

Connect service via proxy
```
$ kubectl proxy
```

## Create application
Create app
```
$ kubectl create -f nginx.yaml
```

Connect service via proxy
```
$ kubectl proxy
```

## Get information
Get pods information
```
$ kubectl get pods
```

Get detailed information
```
$ kubectl describe pods/example-app
```

Get all objects information
```
$ kubectl get all
```

## Controling

Scaling
```
$ kubectl scale deployments/example-app-deploy --replicas=4
```

Rollout
```
$ kubectl set image deployments/example-app-deploy example-app-deploy=nginx:1.9.1
```

Undo rollout
```
$ kubectl rollout undo deployments/example-app-deploy
```
