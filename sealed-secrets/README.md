install server side

```
kubectl apply -f https://github.com/bitnami-labs/sealed-secrets/releases/download/v0.34.0/controller.yaml
```

install client side (dev machine)

```
curl -OL "https://github.com/bitnami-labs/sealed-secrets/releases/download/v0.34.0/kubeseal-0.34.0-linux-amd64.tar.gz"
tar -xvzf kubeseal-0.34.0-linux-amd64.tar.gz kubeseal
sudo install -m 755 kubeseal /usr/local/bin/kubeseal
```