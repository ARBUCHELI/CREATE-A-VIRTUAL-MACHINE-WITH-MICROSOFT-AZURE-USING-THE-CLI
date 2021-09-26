# CREATE-A-VIRTUAL-MACHINE-WITH-MICROSOFT-AZURE

* 1.	First, we'll login using ```az login```
* 2.	Next, we'll create our VM using az vm create. If we don't pass a location, it defaults to the location of the resource group. This would be fine in most cases, but it's worth noting that sometimes a VM size might not be available in the same region as your resource group, so you'd have to pass in a location for a different region.```
az vm create \
   --resource-group "resource-group-west" \
   --name "linux-vm-west" \
   --location "westus2" \
   --image "UbuntuLTS" \
   --size "Standard_B1ls" \
   --admin-username "udacityadmin" \
   --generate-ssh-keys \
   --verbose```
* 3.	Upon success, you will have a JSON response.
* 4.	Next we will open port 80 to allow outside traffic to our VM ```
az vm open-port \
    --port "80" \
    --resource-group "resource-group-west" \
    --name "linux-vm-west"```
* 5.	Upon success, you will receive a JSON response.
