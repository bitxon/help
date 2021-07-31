# Kubernetes

## Base

Set default namespace
```
kubectl config set-context --current --namespace=<NAMESPACE>
```
Get info about objects
```
kubectl get all -o wide
```
Get info about particular object as yaml
```
kubectl get deploy <my-deploy> -o yaml
```

Cleanup
```bash
kubectl delete -f config.yaml
# OR
kubectl delete deployments --all
kubectl delete services --all
kubectl delete pods --all
kubectl delete daemonset --all
```

Apply config from *.yaml file
```bash
# Apply config
kubectl apply -f config.yaml
# Apply Config and save change-cause
kubectl apply -f config.yaml --record=true
```

---
## Rollout

Check history
```bash
# All history
kubectl rollout history deploy
# Paticular revision
kubectl rollout history deploy --revision=3
```

Rollback
```bash
kubectl rollout undo deploy test
```

---
## GCP
Connect kubectl to cluster
```bash
gcloud container clusters get-credentials <my-cluster> --zone <my-zone> --project <my-gcp-project>
```

---
## Quick start

### Simple nginx with NodePort balancer
```bash
# Create Deployment
kubectl create deployment nginx-dep --image=nginx --replicas=2
# Create Service
kubectl expose deployment nginx-dep --name=nginx-dep-svc --type=NodePort --port=80
# OR Just port forward for one pod
kubectl port-forward nginx-dep-5c5477cb4-9g84j 8888:80
```

### Busy box and ping LB
```bash
# Run busybox
kubectl run -i --tty loader --image=busybox /bin/sh
# Find right host
nslookup myservice
# Ping host in a loop
while true; do wget -q -O- http://myservice.default.cluster.local; done
```

### Curl from local machine
```
curl http://$(kubectl get svc/myservice \
    -o jsonpath='{.status.loadBalancer.ingress[0].hostname}'):8080/hello
```

---
## Other

### Windows Docker Desktop metrics-server
1. Download latest component.yaml from [Github metrics-server](https://github.com/kubernetes-sigs/metrics-server#installation)
2. Edit Deployment and add `–kubelet-insecure-tls` flag into args block
    ```yaml
    kind: Deployment
    metadata:
    name: metrics-server
    namespace: kube-system
    ...
    spec:
    ...
    template:
        spec:
        containers:
        - args:
            - --kubelet-insecure-tls # add this flag
    ```
3. Check that metrics-server is working
    ```
    kubectl top node
    ```
