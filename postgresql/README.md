First create namespace, then secret like this:

```
kubectl create secret generic postgres-secret \
  --from-literal=POSTGRES_USER=dummyUser \
  --from-literal=POSTGRES_PASSWORD=dummyPassword
```


Then apply rest of the manifests. The service is headless so other namespaces will be calling postgres like this:

```
nslookup postgres.postgres.svc.cluster.local
```
Where the structure is like this:

```
nslookup <service_name>.<namespace_name>.svc.cluster.local
```