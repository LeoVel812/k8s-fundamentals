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

## exposing ports
* kubectl port-forward deploy/order-serv-deploy 8080:80