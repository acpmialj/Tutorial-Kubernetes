En el portal, crear una storage account standard. Elegir región (westeurope), nombre (ipmdsa) y grupo de recursos (ipmdrg). 

Ir a "Data storage" --> "File shares". Crear un "share" con nombre "myfileshare". Obtener el storage key:



kubectl create secret generic azure-secret \
--from-literal=azurestorageaccountname=ipmdsa \
--from-literal=azurestorageaccountkey=oR0+hRsvUBPhF83BYcKhyLdYAaYCKk5MvVxROcyUa5vvw9g0X0ykTfS04R/E2m2LIF+0NNLAZ/qX+ASttASwRA==
