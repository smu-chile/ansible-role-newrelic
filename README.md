Huawei CCE Setup
=========

Role to setup a bastion to connect with a cce cluster



Role Variables
--------------

```
      NEWRELIC_LICENSE_KEY
      CLUSTER_NAME
      NEWRELIC_API_KEY
      NEWRELIC_DEPLOY_KEY
```

Example Playbook
----------------


```
- hosts: all
  become: no
  remote_user: "root"

# Uncomment "aws-eks-setup" role only if you are upgrading the cluster
  roles:
    - role: ansible-role-newrelic
      NEWRELIC_LICENSE_KEY: "{{ lookup('env', 'NEWRELIC_LICENSE_KEY') }}"
      CLUSTER_NAME: "{{ lookup('env', 'CLUSTER_NAME') }}"
      NEWRELIC_API_KEY: "{{ lookup('env', 'NEWRELIC_API_KEY') }}"
      NEWRELIC_DEPLOY_KEY: "{{ lookup('env', 'NEWRELIC_DEPLOY_KEY') }}"

```

License
-------

BSD

Author Information
------------------

- [César vergara](mailto:cvergarae@smu.cl)

