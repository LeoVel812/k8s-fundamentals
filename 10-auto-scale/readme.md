# Horizontal Pod auto-scaler
## Install metrics sever for kind cluster
* Download file with custom yaml for kind cluster
* Custom it for the latest k8s api for metrics from https://github.com/kubernetes-sigs/metrics-server/releases
* Apply it to the kind server: kubectl apply -f .\resources\metrics-server.yaml


## view metrics:
* kubectl top pod
* kubectl top node