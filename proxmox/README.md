# ansible-proxmox

Ansible playbooks for deploying k8s on Proxmox VM

## Procedures

Gather info

```bash
ansible all -m gather_facts
```

Update apt cache

```bash
ansible all -m apt -a update_cache=true
```

### Setup LXC K8S cluster

To get all availables tags:

```bash
ansible-playbook k8s.yml --list-tags
```

Output:

```
play #1 (pve): Msnage a k8s LXC cluster       TAGS: []
    TASK TAGS: [create, master, remove, start, stop, worker]
```

- `create` - Creates new k8s LXC cluster
- `start` - Creates and Starts new k8s LXC cluster
- `remove` - Removes k8s LXC cluster
- `stop` - Stops k8s LXC cluster
- `master` - All new master container procedures
- `worker` - All new worker container procedures

Then execute a tag. This will create and start all the lxc containers:

```bash
ansible-playbook k8s.yml --tags start
```

To run all the procedures:

```bash
ansible-playbook k8s.yml
```
