# ckad-notes


```

kubectl run nginx-448839 --image nginx:alpine

kubectl create ns apx-z993845





kubectl create deployment httpd-frontend --image httpd:2.4-alpine

kubectl scale deployment  --replicas 3 httpd-frontend


kubectl run --image redis:alpine -l tier=msg


kubectl get rs

kubectl get rs rs-d33393 -o yaml > rs.yaml

kubectl describe rs rs-d33393

kubectl edit rs rs-d33393

kubectl get po | grep rs-d33393

delete pods one at a time

kubectly get po | grep rs-d33393



kubectl -n marketing expose deployment redis --name messaging-service --port 6379 --target-port 6379 --dry-run=client -o yaml > svc.yaml

vi svc.yaml ----> add the namespace field namespace: marketing

kubectl apply -f svc.yaml

kubectl describe svc messaging-service 



kubectl get pods

kubectl get pod webapp-color -o yaml > pod.yaml


spec:
  containers:
  - name: envar-demo-container
    image: gcr.io/google-samples/node-hello:1.0
    env:
    - name: DEMO_GREETING
      value: "Hello from the environment"
    - name: DEMO_FAREWELL
      value: "Such a sweet sorrow"
      
      
      
      
      
kubectl create cm cm-3392845 --from-literal=DB_NAME=SQL3322 etc..





kubectl create secret db-secret-xxdf --from-literal=DB_NAME=SQL3322 etc..


kubectl describe secrets db-secret-xxdf

kubectl get secret -o yaml 





root user, security context





kubectl -n e-commerce logs e-com-1123 > /opt/outputs/e-com-1123.logs





vi pv.yaml


apiVersion: v1
kind: PersistentVolume
metadata:
  name: foo-pv
spec:
  storageClassName: ""
  claimRef:
    name: foo-pvc
    namespace: foo
    
    
  kubectl get pv
  
  
  
  
kubectl create deployment redis --image=redis:alpine

kubectl label deployments.apps redis app=redis

kubectl get deployments.apps --show-labels

kubectl expose deployment redis --target-port 6379 --port 6379

23:41 --> video

kubectl describe netpol redis-access





kubectl run sega --image=busybox --command sleep 3600 --dry-run=client -o yaml > sega.yaml

29:15 --> video


 
 
 
 
 



```









