# issues with only path based routing using nginx-ingress-controller
* with varios namespaces it will use the same home path /, so it won't work
* use host + path based routing 
## namespace
* kubectl create ns dev
* kubectl create ns qa
* kubectl get ns
* kubectl apply -f .\dev-workload\ -n dev
* kubectl apply -f .\dev-workload\ -n qa
* kubectl get all -n dev
* kubectl get ing -n dev
* kubectl get all -n qa
* kubectl get ing -n qa
