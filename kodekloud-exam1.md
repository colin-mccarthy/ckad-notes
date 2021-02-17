# ckad-notes

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









