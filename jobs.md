```
k -n neptune get pod,job | grep neb-new-job
```

```
k -n neptune create job neb-new-job --image=busybox:1.31.0 $do > /opt/course/3/job.yaml -- sh -c "sleep 2 && echo done"
```
