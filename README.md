# Enonic XP on Google Kubernetes Engine (GKE)

Assuming that:
* gcloud tool is set up
* GKE cluster is already created
* kubectl is installed and connected to the GKE cluster

```
gcloud compute disks create --size 50GB enonic-xp-pdisk
```
Default is SATA disk (pd-standard), to use SSD add --type=pd-ssd

```
kubectl create -f enonic-xp-deployment.yaml
```

```
kubectl create -f enonic-xp-dev-service.yaml
```

Watch the service until its created.
```
k get service -w
```

## Optional: TLS from Lets Encrypt with Cert-Manager
* Cert-Manager must be installed on the k8s cluster
* Requires port type NodePort instead of LoadBalancer

```
kubectl create -f enonic-xp-service.yaml
```

```
gcloud compute addresses create xp-diego-cloud-ip --global
```

```
kubectl create -f enonic-xp-ingress.yaml
```


# Cleanup

```
kubectl delete -f enonic-xp-dev-service.yaml
kubectl delete -f  enonic-xp-deployment.yaml
```

```
gcloud compute disks delete enonic-xp-pdisk
```
