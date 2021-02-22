## configMap

Create a configMap from a file with these two env variables in it.

```
COLOR=green
NUMBER="2"
```

Create a pod that uses this config map to get these env vars.





 ## Answer
```
k create cm --help

Examples:
  # Create a new configmap named my-config based on folder bar
  kubectl create configmap my-config --from-file=path/to/bar
 
k create configmap my-config --from-file=path/to/bar  
```




```
apiVersion: v1
kind: Pod
metadata:
  name: pineapple
spec:
  containers:
    - name: pineapple
      image: pihole/pihole
      envFrom:
      - configMapRef:
          name: my-config
  restartPolicy: Never
```
              

```
k exec podname -it -- env
```
