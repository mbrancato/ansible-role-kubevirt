# KubeVirt

This Ansible role will prepare nodes for the deployment of KubeVirt onto an
existing Kubernetes cluster. It supports making necessary changes to the
cluster nodes, which should be configured in the host inventory.

## Requirements

This role has only been tested with Debian, but should support Ubuntu, RHEL,
and CentOS.

* Ansible - 2.9+ recommended

## Variables

The following variables are supported. When using this role, set variables
inside the role context. For example:

```yaml
  roles:
  - name: kubevirt
    vars:
      kubevirt_enable_nested: false
```

### `kubevirt_enable_nested`

- Enables nested virtualization if Kubernetes itself is deployed on virtual
machines
- Default: *true*
