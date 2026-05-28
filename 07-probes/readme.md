# Probe
## httpGet
### retries
* how many times it could fail before killing the container and checks the restart policy
* failureThreshold: 3
### pace of checking the probe
* periodSeconds: 10 
### exec
* less preferable option, but when the pod doesn't have any other alternative, use this probe
* it's recommended to use a custom script inside a image

### liveness probe
* it will be executed after startup probe succeds
* if liveness probe fails when pod is running, it will immediately fail and will restart the pod

### readiness probe
* it will be executed after startup probe succeds
* if readiness probe fails when pod is running, it will keep the pod running but not ready, 
* it won't restart the pod
## describe pod
* kubectl describe pod
## watch pod
* kubectl get pod -o wide -w
## show pod logs
* kubectl logs pod/startup-demo