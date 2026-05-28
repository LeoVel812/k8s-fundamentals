# Namespace
## show
* kubectl get namespace
* kubectl get ns
## create
* kubectl create ns dev
## delete
* kubectl delete ns dev
## get specific k8s object from specific namespace
* kubectl get pod -n kube-system
## create k8s objects on specific namespace
* kubectl create -f .\06-rolling-update-demo.yaml -n qa
## exposing ports on every namespace
* kubectl port-forward svc/my-svc 8080:80 -n qa
* kubectl port-forward svc/my-svc 8080:80 -n dev
## deleting all objecs by spacename
* kubectl delete ns dev
* kubectl delete ns qa
