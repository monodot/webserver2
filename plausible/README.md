# Plausible

Create a file `plausible-conf.env` (there is a `.sample` provided) and then:

```
kubectl create namespace plausible # Create a new namespace for all resources

kubectl -n plausible create secret generic plausible-config --from-env-file=plausible-conf.env

kubectl -n plausible create secret generic plausible-db-user --from-literal='username=postgres' --from-literal='password=postgres' # Create the Postgres user

kubectl -n plausible create secret generic plausible-events-db-user --from-literal='username=clickhouse' --from-literal='password=clickhouse' # Create the Clickhouse user

kubectl -n plausible apply -f .
```
