
# Welcome to launch and configure docker container using ansible

### What we want to do?
  It does below tasks using ansible-playbooks

 - [ ]  Install docker

 - [ ]  Launch container

 - [ ]  Configure container and deploy flask app

  
## How to run?

1. Install docker on server

-  `ansible-playbook docker-configure.yml`

2. Launch docker-container

-  `ansible-playbook docker-container.yml`

3. Deploy flask project on container using ansible

-  `ansible-playbook deploymyapp.yml`

  

## Docker setup

1. Generate ssh-key

-  `ssh-keygen -f ./mycontainerkey`

2. Write Dockerfile


3. Write entrypoint.sh