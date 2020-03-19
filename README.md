# KubeVirt

This Ansible role will deploy KubeVirt onto an existing Kubernetes cluster. It
supports making necessary changes to the cluster nodes, which should be
configured in the host inventory.

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

- Enables nested virtualization is Kubernetes itself is deployed on virtual
machines
- Default: *true*

### `kubevirt_available_timeout`

- The amount of time in seconds to wait for KubeVirt to become available when
deploying the custom resource
- Default: *60*

### `kubevirt_kubeconfig`

- Location of the Kubernetes config file to use when deploying KubeVirt
  - Currently, this only supports the target hosts, so the file must be on the remote host
- Default: *~/.kube/config*
