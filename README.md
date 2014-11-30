ansible-project-boilerplate
===========================

Ansible boilerplate for starting new projects.  
The examples are based on debian/ubuntu, they can be easily adjusted for other distros.

## Folder structure

| dir		| contents									    |
|---------------| ----------------------------------------------------------------------------------|
| environments/ | Configuration for vagrant, development, staging, production or other environments |
| roles/ 	| All ansible configuration modules          					    |
| Vagrantfile	| Configured to initiate local development environment				    |

## Vagrant provisioning
Vagrant is just another ansible environment, I don't like using the builtin provisioning system of vagrant.

```
ansible-playbook -i environments/vagrant/inventory --private-key ~/.vagrant.d/insecure_private_key complete.yml
```

## Adding an environment
1.  Copy the vagrant folder structure in environments to a folder with environment name
2.  Rename the group_vars folder to match the environment
3.  Review all files and update the required to match the nodes

### Example
```
cd environments
cp -Rvp vagrant development
mv development/group_vars/vagrant development/group_vars/development
// Adjust files in development accordingly
```
