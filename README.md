# Mina Testworld-2 Ansible deployment

## Design Philosophy

1. Support both block producer and load tester
1. Allow one server to host multiple nodes
1. Non-Docker deployment

## Deployment process

This script does not take care of the following:

1. Provision and secure your server
2. Install Mina binary https://github.com/MinaProtocol/mina/releases/tag/2.0.0rampup5
3. Handle keys from Mina Foundation
4. Generate libp2p keys

This script assumes the following:

1. Your user name is `ubuntu`
1. You have multiple Mina binary named as `mina1`, `mina2`... at `/usr/local/bin`. One for each process
1. You plan to have mina env files and mina config folders in the `/home/ubuntu/` folder

First, copy the inventory file and make customization

```bash
cp inventory.sample inventory
```

When you are ready install a node, you run something like this:

```bash
ansible-playbook main.yml -e "target=bp1"
ansible-playbook main.yml -e "target=lt2"
```
