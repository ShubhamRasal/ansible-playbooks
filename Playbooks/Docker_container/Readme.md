# Welcome to Ansible using ssh!

1. Generate ssh-key
 `ssh-keygen -f ./mycontainerkey`
 2. Write Dockerfile
 3. Write entrypint script
 4. run docker-configure playbook
 5. run docker-container
      it will create container_inventory file for containers
   6. then configure container using ansible playbook test or apache.yml