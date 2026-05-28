# ConfigMap and secrets
## ConfigMap
- used to store props

## apply configmap
* kubectl apply -f .\01-simple-configmap.yaml
## get configmap
* kubectl get cm
## describe configmap
* kubectl describe cm app-props
## get yaml of configmap
* kubectl get cm kube-root-ca.crt -o yaml
