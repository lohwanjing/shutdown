# shutdown

Usage instructions

Run this command to create the SSH keypair we use to login via ansible

ansible-playbook -i ./inventories/lab/hosts generate_master_ssh_keys.yml 




Add each machine to manage to the [shutdown] group in the inventory file

Run this command to create a user (named devops) on each machine we want to manage and give it just the rights to shutdown the machine. Each machine should be created in the inventory file under the [setup]
If the user is not root, you'll need to change it to the correct user in the yml file

ansible-playbook -i ./inventories/lab/hosts create_user.yml --ask-pass



Run this command to shutdown all VMs

ansible-playbook -i ./inventories/lab/hosts shutdown.yml

