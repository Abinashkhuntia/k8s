#### create Minikube cluster

    minikube start --cpus 4 --memory 8192 --vm-driver hyperkit

#### install Prometheus-operator

###### add repos

    helm repo add prometheus-community https://prometheus-community.github.io/helm-charts
    helm repo add stable https://kubernetes-charts.storage.googleapis.com/
    helm repo update

###### install chart

    helm install prometheus prometheus-community/kube-prometheus-stack

###### install chart with fixed versionk

    helm install prometheus prometheus-community/kube-prometheus-stack --version "9.4.1"


###### Using prometheus to connet monogo db service to that and then scrape the data

1. install the monodb service then use a exporter to (either in helm or by a container to scrape the data )
2. in helm set the uri in values in exporter then expose the servicemoiter .(release : prometheus )
