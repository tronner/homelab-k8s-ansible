# homelab-k8s-ansible
Single node k8s with zfs and kubevirt

Simple instructions:

1. Install debian on a physical or virtual machine with 8 GB RAM or more. 
   Version 11.2 (current stable) works. If using a VM, make sure it supports
   nested virtualization. It needs a second disk (`/dev/sdb`) for data; you can
   change this in `inventory/host_vars`. BE READY TO LOSE ALL DATA ON THIS HOST!
   E.g. don't try it on a dual-boot desktop. No care is taken to tip toe around 
   disks and partitions it doesn't know about. I recommend using a virtual machine
   and taking a snapshot before running the playbook. This way you can start over
   without having to reinstall the OS.
2. Make sure you can ssh into it as user root (without password, using keypair)
3. Add it to ssh config, call it k8s-0001 (or change inventory)
4. On local machine (e.g. laptop): `pip install ansible`
5. On local machine: `ansible-playbook single.yaml`
