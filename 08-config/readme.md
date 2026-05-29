# ConfigMap and secrets
## ConfigMap
- used to store props

## Secrets
### get secrets
* kubectl get secret
### using cli
* kubectl create secret generic my-secret --from-literal=username=leoV --from-literal=password=admin123
### get secrets as yaml
* kubectl get secret -o yaml

## apply configmap
* kubectl apply -f .\01-simple-configmap.yaml
## get configmap
* kubectl get cm
## describe configmap
* kubectl describe cm app-props
## get yaml of configmap
* kubectl get cm kube-root-ca.crt -o yaml
## encode base64
* echo leoV | base64
* echo -n leoV | base64
