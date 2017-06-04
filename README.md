#  OoO ansible test

* Install roles

`$ ansible-galaxy -r requirements.yml install`

* Modify heat parameters
* Provide puppet_environments_repo var for puppetnode (e.g. via ansible-vault)
* Load keys (see README.md in ansible-role-puppetmaster)
* Run:

`$ ansible-playbook site.yml --ask-vault-pass`

## Requirements

* Ansible >= 2.3
* shade >= 1.8.0
