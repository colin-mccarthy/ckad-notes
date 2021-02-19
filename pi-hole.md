```

k create deployment pihole --image=pihole/pihole

k scale deployment pihole --replicas 3




k get deployments --show-labels

k label deployments pihole team=broncos

k get deployments --show-labels







