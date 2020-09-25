# Kubernetes Ansible Playbook

The Ansible Playbook in this repository will set up a Kubernetes cluster, which includes a list of components below:

- Kubernetes
- Helm
- Jenkins
- Keycloak
- MongoDB
- Postgresql
- MongoDB Admin Web App
- Postgresql Admin Web App
- Kubernetes Dashboard

The Helm chart installs all of those components. Users can modify variables in group_vars/all to customize their Kubernetes configuration, such as adjust the node port values in each component, change the component's password, etc.

Currently, this Playbook support to provisioning the above infrastructure in both physical or Virtualbox machines, modifying the "vagrant_machine" variable in group_vars/all to target type of machine when setting up the infrastructure.

## Prerequisites

1. [Install the ansible in both host and remote machine](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html)
2. [Install Python3 in remote machine](https://docs.python.org/3/using/index.html)
3. Update the ansible connection configuration in the 'hosts' file of this Playbook
   > [kubernetes]
   > your_remote_machine_ip ansible_user=your_ssh_user ansible_ssh_pass=your_ssh_password

## Installation

Run the command below to set up the infrastructure

> ansible-playbook -i hosts main.yaml
