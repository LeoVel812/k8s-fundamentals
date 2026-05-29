## get storage class
* kubectl get sc
## get persistent volume claim
* kubectl get pvc
## get persistent volume 
* When the pvc is assigned it is persistent volume
* kubectl get pv
## delete pod
* when only deleting pod, the pvc keeps alive
* kubectl delete pod/my-pod
## delete pvc
* kubectl delete -f .\01-simple-pvc.yaml
## delete all pvc
* kubectl delete pvc --all 
## stateful set
* to DBs or any app which needs to persist a state
### headless svc
* use on pod: nslookup nginx-svc
* specific pod nslookup my-ss-1.nginx-svc
* curl specific pod: curl my-ss-1.nginx-svc curl my-ss-2.nginx-svc curl my-ss-0.nginx-svc