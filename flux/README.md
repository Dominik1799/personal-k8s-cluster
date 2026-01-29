Install flux CLI

https://fluxcd.io/flux/installation/

Run this while connected to the cluster. This creates flux-system namespace with all the resources

```
flux install
```

Create access token for github. Use fine grained access token with permissions from here:

https://fluxcd.io/flux/installation/bootstrap/github/

Then you need to create secret that will be referenced later:

```
kubectl create secret generic github-pat \
  --namespace=flux-system \
  --from-literal=username=<dummyUsername> \
  --from-literal=password=<dummyPat>
```
Then annotate it for flux:

```
kubectl annotate secret github-pat \
  --namespace=flux-system \
  fluxcd.io/secret-type=git
```
