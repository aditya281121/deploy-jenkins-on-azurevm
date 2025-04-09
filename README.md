# Deploy-jenkins-on-azurevm 🚀
   This project mention step by step process to deploy jenkins on Azure virtual machine.

## Configure Azure VM
1. Go to Azure Console
2. Create an Azure VM
3. Make the Azure VM in running state

## Steps to deploy jenkins

1. Connect to the Azure Vm :
    ```
    ssh -i "path_of_pem_file" azureuser@(public_ip_of_vm)
    
2. Install Java :
    ```
    sudo apt update
    sudo apt install openjdk-17-jre

3. Install Jenkins:
    ```
    curl -fsSL https://pkg.jenkins.io/debian/jenkins.io-2023.key | sudo tee \
    /usr/share/keyrings/jenkins-keyring.asc > /dev/null
    echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] \
    https://pkg.jenkins.io/debian binary/ | sudo tee \
    /etc/apt/sources.list.d/jenkins.list > /dev/null
    sudo apt-get update
    sudo apt-get install jenkins

4. Check for the running processes related to jenkins:
    ```
    ps -ef | grep jenkins
