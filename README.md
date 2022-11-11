# Helm commands
helm repo add prometheus-community https://prometheus-community.github.io/helm-charts

helm install my-prometheus prometheus-community/prometheus --version 15.18.0

helm ls --all-namespaces

helm repo  ls

kubectl get storageclass

 helm uninstall my-prometheus --keep-history (deletes a release)

 helm upgrade my-prometheus-dev prometheus-community/prometheus --version 15.10.0 -n dev

 helm history my-prometheus-dev -n dev

 helm rollback my-prometheus-dev -n dev 1

 helm install mywebapp-release webapp1/

 minikube tunnel (tunnel traffic to your LoadBalancer)

 helm upgrade mywebapp-release webapp1/ --values webapp1/values.yaml

 minikube service mywebapp