# Globomantics-Ansible
This is the configuration management for our Globomantics fictional company.

After Provisioning the Infrastructure with either Vagrant or Terraform, the next logical thing to so is configure the different applications and services we want running in our company. And of course secure them with different tools available depending on our use case and best practices.

## Getting Started

- Build the Infrastructure with the Vagrant repository. Make sure to go through the README of that repository.

```git clone https://github.com/dareolu/globomantics-vagrant.git ```

- Login to the client node from the provisioned infrastructure

- Clone this repository on the client machine

- Update the `/etc/hosts` file on the client node to reflect the number of nodes you provisioned

```
10.10.10.31 usa-masternode1
10.10.10.32 usa-masternode2
10.10.10.33 usa-masternode3

10.10.10.41 usa-workernode1
10.10.10.42 usa-workernode2

10.10.10.11 usa-client
```

- Update Ansible Inventory  on `/etc/ansible/hosts` to reflect the number of nodes you provisioned

```
[masters]
usa-masternode1
usa-masternode2
usa-masternode3

[workers]
usa-workernode1
usa-workernode2
usa-workernode3

[client]
usa-client

```

``` git clone https://github.com/dareolu/globomantics-ansible.git ```

-  Update the variables in group_vars/all/vars.yml as desired for the different technologies.


- Deploy the configurations by running the playbook

``` ansible-playbook configure-infrastructure.yml```
