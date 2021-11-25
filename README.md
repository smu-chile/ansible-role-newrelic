Ansible Role Newrelic
=========

Role to setup new relic integration

See more: [Kubernetes integration: install and configure](https://docs.newrelic.com/docs/integrations/kubernetes-integration/installation/kubernetes-integration-install-configure/)



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


Author Information
------------------

- [César vergara](mailto:cvergarae@smu.cl)

