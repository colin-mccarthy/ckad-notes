```
k -n neptune get sa # get overview
k -n neptune get secrets # shows all secrets of namespace
k -n neptune get sa neptune-sa-v2 -o yaml | grep secret -A 2 # shows the secret name
```

```
k -n neptune describe secret neptune-sa-v2-token-lwhhl
```

copy and paste the token
