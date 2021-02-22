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
              

