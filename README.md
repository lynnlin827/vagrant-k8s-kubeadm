# Vagrant k8s kubeadm

Build k8s cluster by kubeadm

## Requirement

* Vagrant

## Run

```shell
$ vagrant up
```

SSH to worker1 and make it join to the k8s cluster.

```shell
$ vagrant ssh worker1
# Find the following command in the output of vagrant up
$ sudo kubeadm join 172.28.128.3:6443 --token wsjgpe.me5mxrka2bi11v3m --discovery-token-ca-cert-hash sha256:0c252721fad65b5d825a9980c76ca131ac8f94f8163a75a77aa4ba2d5fddb9d8
```

SSH to master and check the runnings nodes.

```shell
$ vagrant ssh master
$ sudo su -
$ kubectl get nodes

NAME      STATUS   ROLES    AGE   VERSION
master    Ready    master   17m   v1.13.1
worker1   Ready    <none>   75s   v1.13.1
```
