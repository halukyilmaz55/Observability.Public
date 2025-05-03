
# https://docs.coroot.com/ --> incelemek için dokuman

helm repo add coroot https://coroot.github.io/helm-charts

helm repo update

helm search repo coroot

helm template coroot coroot/coroot --version "0.18.14" -n coroot --output-dir .

rm -rf coroot


# CRD yi silme komutu 
kubectl -n coroot delete coroot coroot




# Manuel Kurulum
helm repo add coroot https://coroot.github.io/helm-charts
helm repo update
kubectl create namespace coroot
helm install coroot coroot/coroot --namespace coroot

#Forward the Coroot port to your machine:
kubectl port-forward -n coroot service/coroot-coroot 8080:8080



