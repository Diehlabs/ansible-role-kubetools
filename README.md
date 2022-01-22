ansible-role-kubetools [![Ansible Test](https://github.com/Diehlabs/ansible-role-kubetools/actions/workflows/test.yml/badge.svg)](https://github.com/Diehlabs/ansible-role-kubetools/actions/workflows/test.yml)
=========

Installs and configures kubectl, helm, etc.
Work in progress, only tested working on Ubuntu Linux so far, 16.04/18.04/20.04

Requirements
------------

Any pre-requisites that may not be covered by Ansible itself or the role should be mentioned here. For instance, if the role uses the EC2 module, it may be a good idea to mention in this section that the boto package is required.

Role Variables
--------------

kubetools_kubectl_version: 1.21.1 (Default)
kubetools_kustomize_version: 4.0.0 (Default)
kubetools_helm_version: 3.7.1 (Default)

kubetools_user_id: chris
kubetools_group_id: chris (Default: "{{ kubetools_user_id }}")
kubetools_shell_type: zsh (Default)
kubetools_bin_dir_win: c:\windows (Default)
kubetools_config_source_dir: "/home/{{ kubetools_user_id }}/k8s-config"
kubetools_kubeconfig_files:
  - admin.kubeconfig (Default)


Dependencies
------------

A list of other roles hosted on Galaxy should go here, plus any details in regards to parameters that may need to be set for other roles, or variables that are used from other roles.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: kubetools, kubetools_user: chris }

License
-------

MIT

Author Information
------------------

Chris Diehl

## TODO
* Clean up vars
* Add Tanzu for other OS
