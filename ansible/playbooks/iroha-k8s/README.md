This will eventually describe usage of this playbook


But for now I'm just adding notes on how to destroy the k8s environment created by iroha, so as to try stuff from scratch without dumpipng and recreating cluster:


```
kubectl -n default delete po,svc,configmap,pvc,pv --all 
kubectl delete -f roles/iroha-k8s/files/k8s-peer-keys.yaml -f roles/iroha-k8s/files/k8s-iroha.yaml 
```
The first one can need several runs, and takes a while for the many resources created so be `kubectl get pvc,pv`'ing or something to ensure they're gone.