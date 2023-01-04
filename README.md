# Windfarm

Modified: 2023-01

Micro-service deployments and automation for aggregation and analysis of propulsion tests.

# Quickstart
1. Install `ansible` for your platform following the instructions [here](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html)
2. Provision the turingpi cluster. You will need to enter the admin password to run the provisioner
```
ansible-playbook playbooks/provisioner.yaml -K
```
3. Install k3s following the instructions [here](https://github.com/k3s-io/k3s-ansible)
