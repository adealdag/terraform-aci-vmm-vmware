# terraform-aci-vmm-vmware

This module creates a VMware vSphere VMM Domain using the standard VDS.

## Usage

```hcl
module "vmm_domain_vmware" {
  source   = "github.com/adealdag/terraform-aci-vmm-vmware"

  name              = "vmm_vds"
  vc_host_or_ip     = "my-vcenter.example.local"
  vc_username       = "username"
  vc_password       = "supersecretpasswd"
  vc_datacenter     = "datacenter-1"
  dvs_version       = "6.5"
  stats_collection  = "enabled"
  management_epg_dn = aci_node_mgmt_epg.oob_mgmt_epg.id
  vlan_pool_dn      = aci_vlan_pool.vmm_vmware.id
}
```