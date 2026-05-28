# Commands for deployment
## Rollouts section
### History of rolllouts
* kubectl rollout history deploy
### rollout to last revision, relatively
* The only usable versions, are the last two, you can only rollback between these.
* kubectl rollout undo deploy/order-serv-deploy 
### rollout to specific revision with annotated metadata on yaml
* First, add these on the deployment yaml file, metadata: 
    * annotations.kubernetes.io/change-cause: "Rolling update to v3"
* Apply this to the revision wanted: kubectl rollout undo deploy/order-serv-deploy --to-revision=1
### Show details of a revision
* kubectl rollout history deploy --revision=4
## min ready seconds
* Seconds that will take the deployment to get ready
    * Add this on spec node: minReadySeconds: 10
## Deployment strategies
### Recreate strategy
* Delete all pods and create new ones
    * Add this spec.strategy.type: Recreate
    * Caution with this strategy, it could the service offline
### Rolling Update strategy
* Gradually roll out the pods, mix of old a new pods
    * Add this spec.strategy.type: RollingUpdate
    * spec.strategy.rollingUpdate.maxSurge: 100% or 1 (it means one replica more)
    * spec.strategy.rollingUpdate.maxUnavailable: 2 (two replicas could be deleted when updating)
    * Caution with this strategy, it could saturate max available connections of DB, services, etc.
## exposing ports
* kubectl port-forward deploy/order-serv-deploy 8080:80
## Watch real-time behavior of a pod
* kubectl get pods -w
## get pod details
* kubectl get pod -o wide