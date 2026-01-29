First install the CRD

```
helm install \
  cert-manager oci://quay.io/jetstack/charts/cert-manager \
  --version v1.19.2 \
  --namespace cert-manager \
  --create-namespace \
  --set crds.enabled=true
```

Then apply cluster-issuer.yaml
```
kubectl apply cluster-issuer.yaml
```