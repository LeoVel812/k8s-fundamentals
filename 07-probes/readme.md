# Probe
## httpGet
### retries
* how many times it could fail before killing the container and checks the restart policy
* failureThreshold: 3
### pace of checking the probe
* periodSeconds: 10 

## describe pod
* kubectl describe pod
## watch pod
* kubectl get pod -o wide -w
## show pod logs
* kubectl logs pod/startup-demo