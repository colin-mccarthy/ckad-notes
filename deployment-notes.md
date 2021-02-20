```
k apply -f deployment.yaml --record=true

k rollout status deployment nodeapp

k rollout history deployment nodeapp

k rollout undo deployment nodeapp

```


```

spec:
  replicas: 3
  strategy:
    type: RollingUpdate
    rollingUpdate:
      maxSurge: 25%
      maxUnavailable: 25%
```
