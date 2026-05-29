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