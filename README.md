Comandos: 

criar uma máquina virtual de 2 núcleos:

az vm create \
    --resource-group learn-044879a5-3e49-4598-ba80-74ac5e15fa23 \
    --name SampleVM2 \
    --image UbuntuLTS \
    --admin-username azureuser \
    --generate-ssh-keys \
    --verbose \
    --size "Standard_DS2_v2"

verificar se o tamanho desejado está disponível no cluster de que faz parte a VM. Podemos fazer isto com o comando vm list-vm-resize-options:

az vm list-vm-resize-options \
    --resource-group learn-044879a5-3e49-4598-ba80-74ac5e15fa23 \
    --name SampleVM \
    --output table
    
    
    Para redimensionar uma VM, utilizamos o comando vm resize.
    
    aumentar para um D2s_v3 com 2 vCores e 8 GB de memória. Escreva este comando no Cloud Shell:
    
    az vm resize \
    --resource-group learn-044879a5-3e49-4598-ba80-74ac5e15fa23 \
    --name SampleVM \
    --size Standard_D2s_v3
    
    
    vm list-ip-addresses, que irá listar os endereços IP público e privado para uma VM.  az vm list-ip-addresses -n SampleVM -o table
    Listar json colorido:  az vm list --output 
    
    obter informações mais detalhadas sobre uma máquina virtual específica pelo nome ou identificação que executa o vm show comando.
    az vm show --resource-group learn-044879a5-3e49-4598-ba80-74ac5e15fa23 --name SampleVM
    
    startar vm específica 

      az vm start \
    --name SampleVM \
    --resource-group learn-044879a5-3e49-4598-ba80-74ac5e15fa23
    
  
    
    az vm open-port \
    --port 80 \
    --resource-group learn-044879a5-3e49-4598-ba80-74ac5e15fa23 \
    --name SampleVM
