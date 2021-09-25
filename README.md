# Rqlite-Helm

WIP: Helm template to set up replicated Rqlite

## Usage

```bash

# deployment
helm template test1 rqlite-helm > test1.yaml
k apply -f test1.yaml

# double checking status of deployment
k describe service test1-rqlite-helm
k get pods -l app.kubernetes.io/instance=test1,app.kubernetes.io/name=rqlite-helm

# using Rqlite
kubectl run my-shell --rm -i --tty --image ubuntu -- bash
curl test1-rqlite-helm:4001/status?pretty

# scaling up
k scale sts test1-rqlite-helm --replicas=2
```
