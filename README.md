ansible-role-kubetools [![Ansible Test](https://github.com/Diehlabs/ansible-role-kubetools/actions/workflows/test.yml/badge.svg)](https://github.com/Diehlabs/ansible-role-kubetools/actions/workflows/test.yml)
=========

Installs and configures kubectl, helm, etc.
Work in progress, only tested working on Ubuntu Linux so far, 16.04/18.04/20.04

Requirements
------------

Any pre-requisites that may not be covered by Ansible itself or the role should be mentioned here. For instance, if the role uses the EC2 module, it may be a good idea to mention in this section that the boto package is required.

Role Variables
--------------

| Variable name | Description | Example value or default if optional | Required? |
|---|---|---|---|
kubetools_kubectl_version | Version of kubectl to install | 1.21.1 | YES |
kubetools_kustomize_version | Version of kustomize to install | 4.4.0 | no |
kubetools_helm_version | Version of helm to install | 3.7.1 | no |
kubetools_argo_version | Version of argo to install | 1.1.1 | no |
kubetools_user_id | The user ID to configure kubetools for | "{{ user_id }}" | YES |
kubetools_group_id | Name of the local group to configure kubetools for | "{{ kubetools_user_gid_by_os[ansible_system] }}" | no |
kubetools_shell_type | Shell that the kubetools_user_id user will use | zsh | no |
kubetools_bin_dir_win | Used for Windows, role not ready for Windows | c:\windows | maybe |
kubetools_config_source_dir | Folder to write kube config files to, if supllied | "~{{ kubetools_user_id }}/.kube" | no |
kubetools_bin_path | Path to store downloaded binaries in | /usr/local/bin/ | no |
kubetools_tanzu_install | Install Tanzu CLI | false | no |
kubetools_kube_conf_files | Dict of file_name=>file_contents of kube config files to manage | see yaml example below | no |

```yaml
kubetools_kube_conf_files:
  config: <raw contents>
  prod_cluster: <raw contents>
  dev_cluster: <raw contents>
  etc...
```

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

[Chris Diehl](https://www.linkedin.com/in/chrisdiehl817/)
