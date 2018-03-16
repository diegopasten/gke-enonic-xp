# Enonic XP on Google Kubernetes Engine (GKE)

Assuming that:
* gcloud tool is set up
* GKE cluster is already created
* kubectl is installed and connected to the GKE cluster

```
gcloud compute disks create --size 50GB enonic-xp-pdisk
```

```
kubectl create -f enonic-xp-deployment.yaml
```

```
kubectl create -f enonic-xp-service.yaml
```

```
gcloud compute addresses create xp-diego-cloud-ip --global
```

```
kubectl create -f enonic-xp-ingress.yaml
```
