---
layout: "openstack"
page_title: "OpenStack: openstack_networking_floatingip_v2"
sidebar_current: "docs-openstack-datasource-networking-floatingip-v2"
description: |-
  Get information on an OpenStack Floating IP.
---

# openstack\_networking\_floatingip\_v2

Use this data source to get the ID of an available OpenStack floating IP.

## Example Usage

```hcl
data "openstack_networking_floatingip_v2" "floatingip_1" {
  address = "192.168.0.4"
}
```

## Argument Reference

* `region` - (Optional) The region in which to obtain the V2 Neutron client.
  A Neutron client is needed to retrieve floating IP ids. If omitted, the
  `region` argument of the provider is used.

* `address` - (Optional) The IP address of the floating IP.

* `pool` - (Optional) The name of the pool from which the floating IP belongs to.

* `port_id` - (Optional) The ID of the port the floating IP is attached.

* `fixed_ip` - (Optional) The specific IP address of the internal port which should be associated with the floating IP.

* `tenant_id` - (Optional) The owner of the floating IP.

## Attributes Reference

`id` is set to the ID of the found floating IP. In addition, the following attributes
are exported:

* `status` - status of the floating IP (ACTIVE/DOWN).
