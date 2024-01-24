# corpsec-vault-module
A Terraform module for Vault. This module will:

  1. Configure `$CORPSEC_VAULT` for a given team or application name
  2. Enable approved secrets engines 
  3. Configure identity trust in target Cloud platforms
  4. Enable dynamic Just in Time secrets, where appropriate

## usage
```terraform
module "my_vault" {
    source ="corpsec-registry/corpsec-vault-module/vault"
    version = "0.0.1"
    name = "example-consumer-team"

    pki_engine = true
    transit_engine = true

    mysql_engine = true
    postgresql_engine = true

    aws = true
    gcp = true
    openstack = true
    k8s = false
} 
```
