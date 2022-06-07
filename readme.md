```
az acr create --resource-group az204-acr-rg --name crspinatose --sku Basic
az acr build --image sample/hello-world:v1 --registry crspinatose --file Dockerfile . 
az acr repository list --name crspinatose --output table 
az acr repository show-tags --name crspinatose --repository sample/hello-world --output table
az acr run --registry crspinatose --cmd '$Registry/sample/hello-world:v1' /dev/null
az group delete --name az204-acr-rg --no-wait
```