# Datadog-Kubernetes-helm
Install Datadog Agent on Kubernetes Using Helm chart

# Insatll HELM chat
helm repo add datadog https://helm.datadoghq.com
helm repo update

# simple basic install
helm install <RELEASE_NAME> \
    --set datadog.appKey=<DATADOG_APP_KEY> \
    --set datadog.site=<DATADOG_SITE> \
    datadog/datadog

    example: 
    helm install datadog \
    --set datadog.appKey=<DATADOG_APP_KEY> \   ### paste your API key
    --set datadog.site=<DATADOG_SITE> \    ### carefully set your datadog site
    datadog/datadog

datadog site reference : https://docs.datadoghq.com/getting_started/site/
datadog API key : https://us5.datadoghq.com/organization-settings/api-keys   

        ###    Replace https://us5.datadoghq.com with your datadog site for API key

# Insatll with Values.yaml

helm show values datadog/datadog > values.yaml 

        # The above command copyies datadog values.yaml to local directory or you can use values.yaml form this repo

  This values.yaml files in enabled with K8S all pod logs
  
  After requied changes apply the values.yaml

        helm install -f .\values.yaml datadog datadog/datadog

# There are lot of configuration available you can refer as per your requirements

Reference Images

Logs:
image.png

