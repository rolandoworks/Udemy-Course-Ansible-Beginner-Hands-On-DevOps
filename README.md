# Udemy-Course-Ansible-Beginner-Hands-On-DevOps
This Udemy Course is an introduction to Ansible for DevOps.

# Motivation: #
This repo contains an Ansible Playbook (deployment/app-deployment.yaml) to deploy an e-commerce web-application on a target server. Below are the required steps to reproduce the app deployment.

## Systems ##
1) To run the Playbook, use an ubuntu 20.04 PC or Server as your Host machine, (aka "controller_server").
2) Use a Centos 9 Stream x64 server as your target server, (aka "target_server").

## Pre-requisites ##
1) Run the following commands on your Host(controller_server) machine.
```
    sudo apt install ansible
    ansible-galaxy collection install community.mysql
    sudo apt -y install sshpass
    git clone https://github.com/rolandoworks/Udemy-Course-Ansible-Beginner-Hands-On-DevOps.git
```

## USAGE: ##
On your Host(controller_server) machine:
    a) Navigate into the /deployment directory of the cloned git project.
    b) Update the connection variables in the inventory.txt, according to your      target_server info (i.e., ansible_host="*" and ansible_ssh_pass="*").
    c) Run the following command to start the app deployment:
    ```
    ansible-playbook -v app-deployment.yaml -i inventory.txt
    ```

### Note: ### After a successful run you'll be able to access the deployed website at
'http://target_server_ip'

In addition, The '/deployment/ansible.cfg' file is used by ansible to establish connection with the target_server, an alternative would be to add the target_server ssh fingerprint to your ~/.ssh/known_hosts.
