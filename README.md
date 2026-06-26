# K5G

K5G is a project aimed at building a simple IMS and 5G infrastructure on top of Kubernetes, with a practical focus on laboratory environments and incremental deployment.

## Project goal

The main goal is to define a reproducible foundation for deploying telecom and networking services in a Kubernetes environment, starting from a local infrastructure that can be validated before scaling to more complex environments.

## Current status

The repository already includes an initial infrastructure based on:

- Vagrant for local VM provisioning
- Ansible for preparing the base operating system
- a role-based structure ready to continue with Kubernetes installation and the rest of the stack

The current infrastructure focuses on a simple single-node control plane for lab purposes, with the first layer of system preparation already automated.

## Repository structure

- [infra](infra/README.md): infrastructure documentation and local automation
- [infra/Vagrantfile](infra/Vagrantfile): VM definition


## Documentation

- [Infrastructure](infra/README.md)
