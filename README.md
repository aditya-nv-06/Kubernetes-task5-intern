# Task5

## Commands to Deploy Resources

### 1. Create the ConfigMap
```shell
kubectl apply -f configmap.yaml
```
Output:
```
configmap/nginx-config created
```

### 2. Create the Deployment
```shell
kubectl apply -f deployment.yaml
```
Output:
```
deployment.apps/nginx-deployment created
```

### 3. Create the Service
```shell
kubectl apply -f service.yaml
```
Output:
```
service/nginx-service created
```

### 4. Check All Resources
```shell
kubectl get all
```
Output (example):
```
NAME                                   READY   STATUS    RESTARTS   AGE
pod/nginx-deployment-xxxxxx-xxxxx      1/1     Running   0          1m
pod/nginx-deployment-xxxxxx-yyyyy      1/1     Running   0          1m

NAME                      TYPE        CLUSTER-IP      EXTERNAL-IP   PORT(S)   AGE
service/nginx-service     ClusterIP   10.0.0.10       <none>        80/TCP    1m

NAME                              READY   UP-TO-DATE   AVAILABLE   AGE
deployment.apps/nginx-deployment  2/2     2            2           1m

NAME                                         DESIRED   CURRENT   READY   AGE
replicaset.apps/nginx-deployment-xxxxxx      2         2         2       1m
```

### 5. Describe Resources
```shell
kubectl describe configmap nginx-config
kubectl describe deployment nginx-deployment
kubectl describe service nginx-service
```
Each will show details and events for the resource.

### 6. Check Pod logs
```shell
kubectl logs <pod-name>
```
Shows logs from the nginx container.

### 7. Port Forwarding
```shell
kubectl port-forward service/nginx-service 8080:80
```
Output:
```
Forwarding from 127.0.0.1:8080 -> 80
Forwarding from [::1]:8080 -> 80
```
