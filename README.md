I'm experimenting with VMs for local development (using VirtualBox and Vagrant); this repo holds the Ansible playbooks that I'm using to provision those VMs.

For example, I've got a VM that just needs nginx (it's for the development of an angular.js app with no server-side component). Here's the relevant bit of the Vagrantfile:

```
config.vm.provision :ansible do |ansible|
  ansible.sudo = true
  ansible.playbook = "~/Projects/ansible/nginx.yml"
  ansible.inventory_file = "ansible_hosts"
end
```

**Note** Vagrant 1.2.7 currently reports successful Ansible runs as failures. Vagrant's master branch has a fix, but it won't be released for a bit.