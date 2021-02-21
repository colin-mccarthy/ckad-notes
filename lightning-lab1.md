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
 
