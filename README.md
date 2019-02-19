# sample-00000

Edit variables in `path/to/roles/iroha-k8s/defaults/main.yml` to your liking

```
ansible-playbook path/to/playbooks/iroha-k8s/main.yml 
```

```
kubectl create configmap iroha-config --from-file=path/to/roles/iroha-k8s/files/conf
```

in that `conf` folder should be the generated genesis block and config file.
After configmap is created, deploy with
```
kubectl apply -f path/to/roles/iroha-k8s/files/k8s-peer-keys.yaml \
                -f path/to/roles/iroha-k8s/files/k8s-iroha.yaml
    
```
