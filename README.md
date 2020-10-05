# Ansible-Azure

# Install Anisble on Mac book 

In order to install Anisble on your mac its always good to create virtual enviroment. 

# For these examples to work, ensure that:
# - you are running Linux or macOS
# - Python 3.6 or 3.7 (NOT 3.8) has been installed
python3 --version

# Create directory for Meltano projects
mkdir ansible-projects
cd ansible-projects

# Create and activate virtual environment
python3 -m venv .venv
source .venv/bin/activate

 cd .venv/
  mkdir .azure
  vi .azure/credentials
[default]
subscription_id=<your-subscription_id>
client_id=<security-principal-appid>
secret=<security-principal-password>
tenant=<security-principal-tenant>

https://galaxy.ansible.com/azure/azcollection?extIdCarryOver=true&sc_cid=701f2000001OH7YAAW

To install Azure dependencies:
```
pip install -r requirements-azure.txt
```
To install Azure collection hosted in Galaxy:
```
ansible-galaxy collection install azure.azcollection
```
To upgrade to the latest version of Azure collection:
```
ansible-galaxy collection install azure.azcollection --force
```
Get the list of all azure moudles 
```
 pip3 list|grep azure
```
you might need install some more moudle i got error to install this 
```
pip install azure-mgmt-privatedns
```

 Run the Ansible command to create Resource Group 
```
 ansible-playbook create_rg.yml --extra-vars "name=ansible location='Australia Southeast'"
 ```