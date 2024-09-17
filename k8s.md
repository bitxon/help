# Kubernetes

## Base

Set default namespace

```shell
kubectl config set-context --current --namespace=<NAMESPACE>
```

Get info about objects

```shell
kubectl get all -o wide
```

Get info about particular object as yaml

```shell
kubectl get deploy <my-deploy> -o yaml
```

Cleanup

```shell
kubectl delete -f config.yaml
# OR
kubectl delete deployments --all
kubectl delete services --all
kubectl delete pods --all
kubectl delete daemonset --all
```

Apply config from \*.yaml file

```shell
# Apply config
kubectl apply -f config.yaml
# Apply Config and save change-cause
kubectl apply -f config.yaml --record=true
```

---

## Rollout

Check history

```shell
# All history
kubectl rollout history deploy
# Paticular revision
kubectl rollout history deploy --revision=3
```

Rollback

```shell
kubectl rollout undo deploy test
```

---

## GCP

Connect kubectl to cluster

```shell
gcloud container clusters get-credentials <my-cluster> --zone <my-zone> --project <my-gcp-project>
```

---

## Quick start

### Simple nginx with NodePort balancer

```shell
# Create Deployment
kubectl create deployment nginx-dep --image=nginx --replicas=2
# Create Service
kubectl expose deployment nginx-dep --name=nginx-dep-svc --type=NodePort --port=80
# OR Just port forward for one pod
kubectl port-forward nginx-dep-5c5477cb4-9g84j 8888:80
```

### Busy box and ping LB

```shell
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
