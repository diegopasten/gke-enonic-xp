gcloud compute disks create --size 200GB enonic-xp-disk
gcloud compute disks create --size 200GB nginx-disk

kubectl create secret generic enonic-xp --from-literal=password="password"

kubectl create -f enonic-xp.yaml

kubectl create -f enonic-xp-service.yaml

kubectl create -f mysql-service.yaml

kubectl create -f nginx.yaml
