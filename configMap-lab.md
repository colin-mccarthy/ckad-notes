```
k create cm --help

Examples:
  # Create a new configmap named my-config based on folder bar
  kubectl create configmap my-config --from-file=path/to/bar
 
k create configmap my-config --from-file=path/to/bar  
```


```
k exec podname -it -- bash bin/sh

k exec podname -it -- env

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
              

