## Setup:

Requirement: Ansible on a virtualenv

```
$ virtualenv --system-site-packages ~/share/env
```

add this to ~/.bashrc:

```
VIRTUAL_ENV_DISABLE_PROMPT=1 . ~/share/env/bin/activate
```

re-logon, then:

```
pip install --upgrade ansible
```

After you checkout, do submodule update:

```shell
$ git submodule update --init --recursive
```

## Usage:

  * Edit ansible.cfg to point to your private key
  * Edit hosts.txt to point to your clusters SSH Addresses
  * Edit etc-hosts.txt to match your cluster layout /etc/hosts content


```shell
$ ansible-playbook -b playbooks/sudo.yml playbooks/cdh-base.yml playbooks/hosts.yml playbooks/cloudera-manager.yml
```

