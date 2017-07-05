# OpenStack on OpenStack

* Install roles

`$ ansible-galaxy -r requirements.yml install`

* Load keys (see README.md in ansible-role-puppetmaster)
* Source openrc
* Provide host_vars (ansible-vault is presumed):
  * puppet_environments_repo
  * vault_openldap_server_rootpw
  * vault_testuser_ldap_pwd
* Run (adding --ask-vault-pass if such in use):

`$ ansible-playbook site.yml`

## Requirements

* Ansible >= 2.3
* shade >= 1.8.0
