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

 # Create the helmchart
```
helm create webapp1
```


# Follow along with the video
- Create the files per the video, copying and pasting from templates-original
- you can also use the files in the solution folder

# Install the first one
```
helm install mywebapp-release webapp1/ --values mywebapp/values.yaml
```

# Upgrade after templating
```
helm upgrade mywebapp-release webapp1/ --values mywebapp/values.yaml
```

# Accessing it
```
minikube tunnel
```

# Create dev/prod
```
k create namespace dev
k create namespace prod
helm install mywebapp-release-dev webapp1/ --values webapp1/values.yaml -f webapp1/values-dev.yaml -n dev
helm install mywebapp-release-prod webapp1/ --values webapp1/values.yaml -f webapp1/values-prod.yaml -n prod
helm ls --all-namespaces
```