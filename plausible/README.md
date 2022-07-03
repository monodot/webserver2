# Plausible

Create a file `plausible-conf.env` (there is a `.sample` provided) and then:

```
kubectl create namespace plausible # Create a new namespace for all resources

kubectl -n plausible create secret generic plausible-config --from-env-file=plausible-conf.env

kubectl -n plausible create secret generic plausible-db-user --from-literal='username=postgres' --from-literal='password=postgres' # Create the Postgres user

kubectl -n plausible create secret generic plausible-events-db-user --from-literal='username=clickhouse' --from-literal='password=clickhouse' # Create the Clickhouse user

kubectl -n plausible apply -f .
```

**IMPORTANT:** Plausible needs to know the visitor's IP address in order to resolve their country. If running on k3s, you can patch the default installation of Traefik, so that it will pass on the user's real IP address in the header, instead of an internal cluster IP:

```
kubectl patch deployment traefik --patch '{"spec":{"template":{"spec":{"hostNetwork":true}}}}' -n kube-system
```

H/T: <https://github.com/k3s-io/k3s/discussions/2997#discussioncomment-1617536>

