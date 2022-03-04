# rook-ceph-disk-prepare
quick role to prepare disks for k3s/k8s deployment

Idea for role "k3s_disks" is to partition disks, before ansible k3s deployment (or k8s, doesn't really matter).
Prerequsite is running linux system with couple tools like parted, fdisk etc
In this scenario /var/lib/rancher is used as example, for placing ephemeral storage on different partition.
To successfully run the role two things need to be done:
  - change variable "reconfigure_disks" in inventory file for node prepared to partition
  - review the configuration inside k3s_disks/vars/{k3s_env}/sd{a,b,c...}.yaml


## TODO
  - move devices (sda, sdb etc) into inventory file
  - modify role to get different disk configs for different nodes
  - add lvm support

  - add rook-ceph role
  - add jinja for values.yaml for rook-ceph deploy
