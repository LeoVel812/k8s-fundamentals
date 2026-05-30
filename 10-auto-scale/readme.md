# Horizontal Pod auto-scaler
## Install metrics sever for kind cluster
* Download file with custom yaml for kind cluster
* Custom it for the latest k8s api for metrics from https://github.com/kubernetes-sigs/metrics-server/releases
* Apply it to the kind server: kubectl apply -f .\resources\metrics-server.yaml


## view metrics:
* kubectl top pod
* kubectl top node
## view hpa
* kubectl get hpa
# view all pods of kube-system
* kubectl get pod -n kube-system, 
* check metrics-server
## using ApacheBench on pod to test load on svc with hpa
* apply service, apply hpa
* execute demo pod of k8s cluster: kubectl exec -it demo-pod -- bash
* execute the benchmark 20,000 requests by 5 users: ab -n 20000 -c 5 http://nginx-svc/
* check metrics with installed metrics-server and kubectl get all
* if a pod is without readiness probe, it will lose requests
* i.e. for ApacheBench, the test will not be finish, it will be a connection refused