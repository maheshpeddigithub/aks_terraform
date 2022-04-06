https://learnk8s.io/terraform-aks

az acr login --name cloudmahesh

docker build -t simple-nginx .

docker tag simple-nginx cloudmahesh.azurecr.io/simple-nginx:v1

docker push cloudmahesh.azurecr.io/simple-nginx:v1

az role assignment list --scope /subscriptions/1f2912d4-eb09-40e0-a7ca-d3059a65e862/resourceGroups/learnk8sResourceGroup/providers/Microsoft.ContainerRegistry/registries/cloudmahesh -o table

az aks update -n learnk8scluster -g learnk8sResourceGroup --attach-acr cloudmahesh