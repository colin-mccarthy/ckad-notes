## Volumes

```
apiVersion: v1
kind: PersistentVolume
metadata:
  name: log-volume
spec:
  capacity:
    storage: 1Gi
  volumeMode: Filesystem
  accessModes:
    - ReadWriteMany
  storageClassName: manual
  hostPath:
    path: /opt/volume/nginx    
```

```
apiVersion: v1
kind: PersistentVolumeClaim
metadata:
  name: log-claim
spec:
  accessModes:
    - ReadWriteMany
  volumeMode: Filesystem
  resources:
    requests:
      storage: 200Mi
  storageClassName: manual
```
 
```
apiVersion: v1
kind: Pod
metadata:
  name: logger
spec:
  containers:
    - name: logger
      image: nginx:alpine
      volumeMounts:
      - mountPath: "/var/www/nginx"
        name: log
  volumes:
    - name: mypd
      persistentVolumeClaim:
        claimName: log-claim
```
 
 
 ## Network Policy 
 
 
 
 ```
 k exec -it web-color -- sh
 
 nc -z -v secure-service 80
 
 cntr z
 
 k get netpol
 
 k describe netpol default-deny 
 
 k get netpol default-deny -o yaml > netpol.yaml
 
 k get po --show-labels
 ```
 
 ```
 apiVersion: networking.k8s.io/v1
kind: NetworkPolicy
metadata:
  name: allow-color
  namespace: default
spec:
  podSelector:
    matchLabels:
      run: secure-pod
  policyTypes:
  - Ingress
    - from:
      - podSelector:
          matchLabels:
            name: webapp-color
      ports:
      - protocol: TCP
        port: 80
```
```
 k exec -it web-color -- sh
 
 nc -z -v secure-service 80
 
 cntr z
``` 

## configMap

```
k create ns dvl1987

k -n dvl1987 create cm time-config --from-literal=TIME_FREQ=10

k run time-check --image busybox -o yaml > time-check.yaml 
```

```
apiVersion: v1
kind: Job
metadata:
  name: time-check
spec:
  template:
    spec:
      containers:
      - name: time-check
        image: busybox
        command: ['sh', '-c', 'echo "Hello, Kubernetes!" && sleep 3600']
      restartPolicy: OnFailure
```

15:10 ---> start here when completing these notes


