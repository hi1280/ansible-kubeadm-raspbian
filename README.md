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

## Troubleshooting

### pod network

pod network is not working

```sh
$ kubectl delete -f https://raw.githubusercontent.com/coreos/flannel/master/Documentation/kube-flannel.yml

$ ssh pi@192.168.3.100 -i ~/.ssh/id_rsa
$ sudo ip link delete cni0
$ sudo ip link delete flannel.1
$ sudo ip link delete veth*
$ exit

$ ssh pi@192.168.3.101 -i ~/.ssh/id_rsa
$ sudo ip link delete cni0
$ sudo ip link delete flannel.1
$ sudo ip link delete veth*
$ exit

$ ssh pi@192.168.3.102 -i ~/.ssh/id_rsa
$ sudo ip link delete cni0
$ sudo ip link delete flannel.1
$ sudo ip link delete veth*
$ exit

$ kubectl apply -f https://raw.githubusercontent.com/coreos/flannel/master/Documentation/kube-flannel.yml
```
