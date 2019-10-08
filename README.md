# Build a Kubernetes cluster using k3s via Ansible.

> This repository is now part of https://github.com/rancher/k3s official repo in contrib/ansible directory.
> Anyway I'll write updates in order to make PM in k3s.
> Be my guest and feel free to contribute.

## My blog post about these bunch of playbooks

Here is my post about [k3s and Ansible provisionning](https://www.it-wars.com/posts/cloud-native/kubernetes-avec-k3s-pour-sauver-la-planete/) (in French)

## K3s Ansible Playbook

Build a Kubernetes cluster using Ansible with k3s. The goal is easily install a Kubernetes cluster on machines running:

- [X] Debian 9
- [ ] Ubuntu 16.04
- [ ] CentOS 7

on processor architecture:

- [X] x64
- [X] arm64
- [X] armhf

## System requirements:

Deployment environment must have Ansible 2.4.0+
Master and nodes must have passwordless SSH access

## Usage

Add the system information gathered above into a file called hosts.ini. For example:

```
[master]
192.16.35.12

[node]
192.16.35.[10:11]

[kube_cluster:children]
master
node
```

Start provisioning of the cluster using the following command:

```
ansible-playbook site.yml
```

