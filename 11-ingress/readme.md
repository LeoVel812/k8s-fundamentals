# Ingress using nginx
* Recreate cluster with new config, apply ingress-nginx


## get namespaces
* kubectl get ns
* check that this ingress-nginx ns exists
## view metrics:
* kubectl top pod
* kubectl top node
## get ingress
* kubectl get ing
## For troubleshooting
* kubectl get pods -n ingress-nginx : ensure the ingress controller pods are running and ready
* kubectl get svc -n ingress-nginx : verify the controller service exists and is exposing port 80/443
* kubectl get ingress : verify my-ingress exists and has an ADDRESS
* kubectl describe ingress my-ingress : look for events that show the controller rejected/ignored it
* kubectl get ingressclass : see which ingress class is available and whether it is default
* kubectl logs -n ingress-nginx deployment/ingress-nginx-controller : look for messages about ignored ingress resources or class mismatch
* kubectl describe ingress my-ingress : after applying, verify Ingress Class: ngin
## more commands
* kubectl get endpoints my-app -o wide
* kubectl get svc my-app -o yaml
* kubectl get pods -l app=my-app -o wide --show-labels
* kubectl describe svc ingress-nginx-controller -n ingress-nginx
* curl from powershell curl.exe -v http://localhost:30153/ 
* kubectl logs -n ingress-nginx deployment/ingress-nginx-controller -f

# when curling and receiving an empty response
* it looks like the 01-cluster config doesn't set 'ingress-ready' and it nevers allows the requests from outside or host machine
* check the label is on true with: kubectl get nodes --show-labels  
* after kind create, apply nginx-ingress from github repo, and apply the files for deploy with ingress, apply the following patch:
* it also could be set with the patch.json with: kubectl patch deployment ingress-nginx-controller -n ingress-nginx --type='json' --patch-file .\patch\patch.json

## applying nginx ingress controller 
* download: curl.exe -L -o .\resources\nginx-ingress-controller-deploy.yaml https://raw.githubusercontent.com/kubernetes/ingress-nginx/main/deploy/static/provider/kind/deploy.yaml
* apply: kubectl apply -f .\resources\nginx-ingress-controller-deploy.yaml