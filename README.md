# Ansible Workstation

This repo is used to build out various ansible roles I need to manage my homelab infrastructure. These are meant to serve as examples of how to strucure ansible IaC for future projects. 

## Printing Facts 

When building roles/playbooks, it's often nice to be able to list all the facts gathered by ansible. This can be done with an ad-hoc command by using the `setup` module. 

```
ansible myhost -m setup
```

## Running Ansible in a Docker Container 

More to come on this.

```
docker run \
  -v "${PWD}":/work:ro \
  -v ~/.ansible/roles:/root/.ansible/roles \
  -v ~/.ssh:/root/.ssh:ro \
  --rm ansible:latest ansible-playbook -i inventory/rke2-cluster/hosts.ini playbooks/update.yml
```
