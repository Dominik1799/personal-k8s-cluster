First, get current yaml values:

```
helm get values traefik -n kube-system -o yaml > traefik-current-values.yaml
```

Then upgrade the traefik deployment:

```
helm upgrade traefik traefik/traefik -n kube-system -f traefik/traefik-current-values.yaml
```

Might also need to add traefik repo first:

```
helm repo add traefik https://traefik.github.io/charts
```