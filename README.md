# Building Kubernetes Cluster with Raspberry Pi

## Install

ansible

```sh
$ brew install ansible
```

## Usage

```sh
$ ansible-playbook -i hosts control-plane-playbook.yml
$ ansible-playbook -i hosts node-playbook.yml
```
