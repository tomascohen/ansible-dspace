# ansible-dspace
Ansible playbook for deploying DSpace for dev use.
===

This role is provided for deploying DSpace on your server. It follows the
install instructions step by step.

The default settings can be checked on the vars/defaults.yml file, and set
on the vars/user.yml file.

For using it you need to create an Ansible playbook. An example is provided

Note: it installs PostgreSQL on the VM.

## Usage example

To use this role you need to build your own playbook like this:

<pre>---
# This is the top-level playbook for deploying Bokeh at UNC

- hosts: vagrant
  user: vagrantusr
  sudo: True
  gather_facts: True
  vars_files:
      - vars/defaults.yml
      - vars/user.yml

  roles:
      - dspace
</pre>
