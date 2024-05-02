# ansible k8s 

Ansible playbooks for setting up k8s VMS

## Procedures

Check inventory file in `inventory/main.yml`

Ping vms

```bash
ansible all -m ping
```

Update apt cache on VMS (become root required)

```bash
ansible all -m apt -a update_cache=true --become
```

### 1. Setup Vms

Setup VMS

```bash
ansible-playbook 1-setup-vm.yml 
```

### 2. Init Cluster

Setup VMS

```bash
ansible-playbook 2-init-cluster.yml 
```


### 3. Init Masters

Setup VMS

```bash
ansible-playbook 3-init-masters.yml 
```
