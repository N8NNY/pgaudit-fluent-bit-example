# pgAudit and fluent-bit example

## Requirements
- Ansible >= 2.11.4
- Python3
- Vagrant and libvirt provider for setup development environment.

## Prepare Vagrant
- Interface
```bash
export VAGRANT_BRIDGE_IF=<your-interface>
```
- SSH public key
```bash
export VAGRANT_PUB_KEY=<your-pub-key>
```
- Start Vagrant
```bash
vagrant up
```

## Deploy example
```bash
ansible-playbook -i hosts -u vagrant all.yml 
```
