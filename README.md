# Kubernetes_en_Azur

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
