ansible-role-kubetools
=========

Installs and configures kubectl, helm, etc.
Work in progress, only tested working on Ubuntu Linux so far, 16.04/18.04/20.04

Requirements
------------

Any pre-requisites that may not be covered by Ansible itself or the role should be mentioned here. For instance, if the role uses the EC2 module, it may be a good idea to mention in this section that the boto package is required.

Role Variables
--------------

kubectl_version: 1.21.1 (Default)
kustomize_version: 4.0.0 (Default)
helm_version: 3.7.1 (Default)

kctl_user_id: chris
kctl_group_id: chris (Default: "{{ kctl_user_id }}")
kctl_shell_type: zsh (Default)
kctl_bin_dir_win: c:\windows (Default)
kctl_config_source_dir: "/home/{{ kctl_user_id }}/k8s-config"
kctl_kubeconfig_files:
  - admin.kubeconfig (Default)


Dependencies
------------

A list of other roles hosted on Galaxy should go here, plus any details in regards to parameters that may need to be set for other roles, or variables that are used from other roles.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: kubetools, kctl_user: chris }

License
-------

MIT

Author Information
------------------

Chris Diehl
