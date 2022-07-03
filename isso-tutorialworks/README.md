# isso for tutorialworks

```
kubectl create ns isso-tw

export SMTP_USERNAME=
export SMTP_PASSWORD=
export SMTP_SERVER=
export SMTP_PORT=
export SMTP_SECURITY=
export SMTP_EMAIL=
export ADMIN_PASSWORD=

cat isso-secret.yaml | envsubst | kubectl apply -n isso-tw -f -

kubectl apply -n isso-tw -f isso.yaml
kubectl apply -n isso-tw -f isso-smtp.yaml

```

