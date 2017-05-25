#  OoO ansible test

*This is still a work in progress and the description below might not be up to
date (yet)*

* Install roles

`$ ansible-galaxy -r requirements.yml install`

* Add vault file providing vault_puppet_environments_repo var for puppet_node
* Load keys (see readme in ansible-role-puppetmaster)
* Run:

`$ ansible-playbook site.yml --ask-vault-pass`

## Requirements

* Ansible >= 2.2
* shade >= 1.8.0
