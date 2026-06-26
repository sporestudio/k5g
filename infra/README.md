# Infra k5g

This directory contains the base infrastructure for deploying a local Kubernetes lab for the K5G project. The current objective is to provision a reproducible control-plane node with Vagrant and Ansible before completing the Kubernetes installation and the higher-level platform services.

## Infrastructure structure

- `Vagrantfile`: defines the VM and initial provisioning
- `ansible.cfg`: shared Ansible configuration
- `ansible/inventory.yml`: host inventory
- `ansible/site.yml`: main playbook
- `ansible/roles/common/`: base system preparation tasks
- `ansible/roles/containerd/`, `ansible/roles/control_plane/`, `ansible/roles/k8s/`, and `ansible/roles/worker/`: placeholder roles for extending the deployment

## How it works

1. Vagrant creates the `k8s-master` VM.
2. Vagrant invokes Ansible with the playbook under `ansible/site.yml`.
3. The `common` role prepares the operating system for Kubernetes.
4. The infrastructure is now ready for the next phase:
   - install `containerd`
   - install `kubeadm`, `kubelet`, and `kubectl`
   - initialize the Kubernetes control plane
   - join worker nodes

## Requirements

- Vagrant
- VirtualBox or another compatible provider
- Ansible (executed automatically by Vagrant)

## Quick start

```bash
cd infra
vagrant up
```

Then:

```bash
vagrant ssh
```

To clean up:

```bash
vagrant destroy -f
```
