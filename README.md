# Kubernetes_en_Azure

Más información en https://learn.microsoft.com/en-us/azure/aks/learn/quick-kubernetes-deploy-portal?tabs=azure-cli 

Crear una instancia de “Servicio de Kubernetes”. Indicar un grupo de recursos. Elegir un cluster lo más pequeño posible (tamaño de nodo Standard_DS2_v2. West Europe. 1 único nodo (por cuotas). Permite hasta 110 pods por nodo. Escalado automático. 

Tras crearlo, conectarse vía Shell.

“az aks get-credentials --resource-group myResourceGroup --name myAKSCluster”

“kubectl get nodes”

“nano azure-vote.yaml” 

“kubectl apply -f azure-vote.yaml”

“kubectl get service azure-vote-front --watch" Indica una dirección IP pública

Desde un navegador  http://dir_publica

Se puede eliminar el cluster eliminando el grupo de recursos. 

“az group delete --name myResourceGroup --yes --no-wait” 

El fichero .yaml indica que se crea lo siguiente:

1. Aplicación “azure-vote-back”. Un back-end basado en un almacén de datos en memoria, Redis. Se especifica una réplica.
2. Servicio “azure-vote-back”, que especifica el puerto de acceso a la aplicación anterior. 
3. Aplicación “azure-vote-front”, el front-end web. Una un contenedor “azure-vote-front”.
4. Servicio “azure-vote-front” asociado a la aplicación anterior. Es de tipo “LoadBalancer”, lo que significa que solicita al proveedor Cloud (Azure) una dirección IP pública y el tráfico que llega a ella por el puerto 80 se redirige de forma balanceada a las instancias de la aplicación “azure-vote-front”.  

