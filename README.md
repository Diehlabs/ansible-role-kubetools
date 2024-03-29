# ansible-role-kubetools
[![Ansible CI](https://github.com/Diehlabs/ansible-role-kubetools/actions/workflows/ci.yml/badge.svg)](https://github.com/Diehlabs/ansible-role-kubetools/actions/workflows/ci.yml)
=========

Installs and configures kubectl, helm, etc.
Tested on Ubuntu Linux 20.04 and various late MacOS versions.

When used with Ubuntu-20.04 in WSL, you must first remove /usr/local/bin/kubectl or use a non-default value for variable "kubetools_bin_path".

## TODO
* Ensure shell completions are installed for all tools
* Add Krew
* Add k9s

Requirements
------------

None.

Role Variables
--------------

| Variable name | Description | Example value or default if optional | Required? |
|---|---|---|---|
kubetools_kubectl_version | Version of kubectl to install | 1.21.1 | YES |
kubetools_argo_version | Version of argo to install | 1.1.1 | no |
kubetools_azwi_version | Version of azwi to install | 0.10.0 | no |
kubetools_istioctl_version | Version of istioctl to install | 1.14.1 | no |
kubetools_helm_version | Version of helm to install | 3.7.1 | no |
kubetools_kustomize_version | Version of kustomize to install | 4.4.0 | no |
kubetools_user_id | The user ID to configure kubetools for | "{{ user_id }}" | YES |
kubetools_group_id | Name of the local group to configure kubetools for | "{{ kubetools_user_gid_by_os[ansible_system] }}" | no |
kubetools_shell_type | Shell that the kubetools_user_id user will use | zsh | no |
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

None.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: localhost
      roles:
         - { role: kubetools, kubetools_user: chrisdiehl }

License
-------

MIT

Author Information
------------------

[Chris Diehl](https://www.linkedin.com/in/chrisdiehl817/)
