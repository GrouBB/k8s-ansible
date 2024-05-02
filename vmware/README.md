# ansible-vmware

Ansible playbooks for deploting k8s on Vmware ESXI and vSphere

## Get info for VC

See inventory

```bash
ansible -i inventory/vc.yml all --list-hosts
```

Run to get info

```bash
ansible-playbook playbook/vc_info.yml
```

## Get info for k8s cluster

```bash
ansible -i inventory/k8s.yml all --list-hosts
```

### Issues

- pyvmomi does not allow vSphere API access to free ESXi. You can read more [about this restriction](https://github.com/ansible/ansible/issues/42262#issuecomment-512876488)
