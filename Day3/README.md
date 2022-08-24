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

## Listing the deployment in default namespace
```
kubectl get deployments
kubectl get deployment
kubectl get deploy
```

Expected output
<pre>
[jegan@localhost ~]$ kubectl get deployments
NAME    READY   UP-TO-DATE   AVAILABLE   AGE
nginx   1/1     1            1           2m49s
[jegan@localhost ~]$ kubectl get deployment
NAME    READY   UP-TO-DATE   AVAILABLE   AGE
nginx   1/1     1            1           2m51s
[jegan@localhost ~]$ kubectl get deploy
NAME    READY   UP-TO-DATE   AVAILABLE   AGE
nginx   1/1     1            1           2m54s
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
