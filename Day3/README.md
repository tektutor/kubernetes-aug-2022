# Day 3 - Kubernetes


## Kubernetes Commands

Listing Kubernetes nodes 
```
kubectl get nodes
```

## Creating our first nginx web server deployment
```
kubectl create deployment nginx --image=nginx:1.18
```
Expected output
<pre>
[jegan@localhost ~]$ kubectl create deployment nginx --image=nginx:1.18
deployment.apps/nginx created
</pre>

## Listing all pods running in default namespace
```
kubectl get pods
kubectl get pod
kubectl get po
```

Expected output
<pre>

</pre>
