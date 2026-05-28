# Commands for services
## Deploying a service
### describe a service
* kubectl describe svc nginx-service

## get a bash from a pod
* kubectl exec -it demo-pod -- bash
## curl a service from a bash pod
* curl my-svc
## exposing ports
* kubectl port-forward deploy/assignment-dp 8080:8080