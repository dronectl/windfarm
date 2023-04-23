# Windfarm
[![ci](https://github.com/dronectl/windfarm/actions/workflows/ci.yaml/badge.svg)](https://github.com/dronectl/windfarm/actions/workflows/ci.yaml)

Modified: 2023-01

Micro-service deployment manifests and automation for in-house test infrastructure. 

# Hardware
The in-house servers are 7 RPi CM3B+ modules on a TuringPi v1.1 Motherboard.

# Installing K3S
1. Install `ansible` for your platform following the instructions [here](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html)
2. Copy the sample inventory directory and update the appropriate fields in the `inventory.yaml` to describe the desired topology
```bash
cp -R ansible/inventory/sample ansible/inventory/my-cluster
```
3. Install k3s on the turingpi cluster with the `k3s.yml` playbook.
```
ansible-playbook playbooks/k3s.yml -i inventory/sample/inventory.yaml
```

Teardown the k3s on the turingpi cluster with the `reset-k3s.yml` playbook.
```
ansible-playbook playbooks/reset-k3s.yml -i inventory/sample/inventory.yaml
```

# Monitoring Deployment
The cluster monitoring deployments are adapted from [here](https://github.com/carlosedp/cluster-monitoring). Follow the instructions in the [README](k3s/monitoring/Readme.md) for installation on a K3S cluster.
