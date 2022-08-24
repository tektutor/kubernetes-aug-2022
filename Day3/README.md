# Day 3 - Kubernetes


## Kubernetes Commands

Listing Kubernetes nodes 
```
kubectl get nodes
```

## Listing the Pods running in kube-system namespaces
```
kubectl get po -n kube-system
```

Expected output
<pre>
[jegan@localhost ~]$ kubectl get po -n kube-system
NAME                               READY   STATUS    RESTARTS       AGE
coredns-6d4b75cb6d-pf2sp           1/1     Running   1 (117m ago)   124m
<b>etcd-minikube                      1/1     Running   1 (118m ago)   124m</b>
<b>kube-apiserver-minikube            1/1     Running   1 (35m ago)    124m</b>
<b>kube-controller-manager-minikube   1/1     Running   1 (118m ago)   124m</b>
kube-proxy-fn5ts                   1/1     Running   1 (118m ago)   124m
<b>kube-scheduler-minikube            1/1     Running   1 (35m ago)    124m</b>
storage-provisioner                1/1     Running   3 (34m ago)    124m
</pre>

In the above output, the highlighted pods are the Control Plane components.

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

## Listing the replicasets in default namespaces
```
kubectl get replicasets
kubectl get replicaset
kubectl get rs
```

Expected output
<pre>
jegan@localhost ~]$ kubectl get replicasets
NAME               DESIRED   CURRENT   READY   AGE
nginx-55fb6488cb   1         1         1       5m17s
[jegan@localhost ~]$ kubectl get replicaset
NAME               DESIRED   CURRENT   READY   AGE
nginx-55fb6488cb   1         1         1       5m19s
[jegan@localhost ~]$ kubectl get rs
NAME               DESIRED   CURRENT   READY   AGE
nginx-55fb6488cb   1         1         1       5m22s
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


## What happens behind this command
```
kubectl create deployment nginx --image=nginx:1.18
```

<pre>
1. kubectl will make a REST API call to API Server(Control Plane Component) running on the master node, requesting to create a deployment by name 'nginx' that uses Docker Image 'nginx:1.18' from Docker Hub.
2. API Server, receives the request from kubectl, it then creates a YAML/JSON record in the etcd database.
3. API Server triggers an event something like "New Deployment Created"
4. Deployment Controller receives the event "New Deployment Created", it then makes a REST call to API Server requesting the API Server to create a ReplicaSet by name 'nginx-<pod-template-hash>'.
5. API Server receives this request, it creates an new ReplicaSet entry in the etcd database.
6. API Server triggers an event something like "New ReplicaSet Created"
7. ReplicaSet Controller receives the event "New ReplicaSet Creted", it fetches the number of Pods it is supposed to create, also it retrieves the Container Image it is supposed to be using to create the Pods. 
8. ReplicaSet Controller makes a REST call to API Server to create so many Pods as mentioned in the event with the appropriate Container Image mentioned in the event.
9. API Server receives the request and creates so many Pod entries in the etcd database.
10. API Server triggers an event for each Pod created in the etcd something like "New Pod Created".
11. Scheduler receives the event, it then identifies a healthy node where those individual Pods can be deployment.
12. Scheduler makes a REST call to API Server sending the Pod scheduling recommendations.
13. API Server receives the scheduling recommendation from Scheduler, API Server retrieves the respective Pod entries from the etcd database, updates the Scheduling the information recommended by Scheduler.
14. API Server triggers an event something like "Pod Scheduled on Node1", "Pod scheduled on Node2", etc.,
15. kubelet the Kuberneter Container Agent that runs on every Node receives those events.  If the Pod is scheduled onto the node where the kubelet is running, then the kubelet with the help of the Container Runtime, pulls the image and creates the pod containers.
16. kubelet constantly monitors the health and status of the Pod Container and keeps sending heart-beat status to API Server.
17. API Server receives the status updates from kubelet from each nodes and it updates the Pod entries with the status information in the etcd database.
</pre>

## Scaling up a deployment
```
kubectl scale deploy/nginx --replicas=3
```

## Creating a ClusterIP Internal service
```
kubectl expose deploy/nginx --type=ClusterIP --port=80
```

Listing the service
```
kubectl get services
kubectl get service
kubectl get svc
```

Finding more details about a service
```
kubeclt describe svc/nginx
```

## Deleting a pod

List the pod
```
kubectl get po
```

Delete a pod
```
kubectl delete pod/<your-pod-name>
```

## Deleting a deployment
Listing a deployment
```
kubectl get deploy
```

Delete a deployment
```
kubectl delete deploy/<your-deployment-name>
```

## Deleting a Replicaset
```
kubectl delete rs/<your-resplicaset-name>
```
