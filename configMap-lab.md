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
spec:
  containers:
    - name: demo
      image: alpine
      command: ["sleep", "3600"]
      env:
          valueFrom:
            configMapKeyRef:
              name: game-demo 
```
              

