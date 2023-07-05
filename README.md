# Resource Groups

This terraform module enables the efficient creation and management of azure resource groups. By offering customizable options for the name, location, management locks and tags, it brings granular control over your azure environment. Resource groups, functioning as logical containers, are essential for managing workloads and deploying accelerators.

## Goals

The main objective is to create a more logic data structure, achieved by combining and grouping related resources together in a complex object.

The structure of the module promotes reusability. It's intended to be a repeatable component, simplifying the process of building diverse workloads and platform accelerators consistently.

A primary goal is to utilize keys and values in the object that correspond to the REST API's structure. This enables us to carry out iterations, increasing its practical value as time goes on.

A last key goal is to separate logic from configuration in the module, thereby enhancing its scalability, ease of customization, and manageability.

## Features

- provides support for both single and multiple resource groups, allowing flexible resource management.
- implements optional management locks for enhanced security

The below examples shows the usage when consuming the module:

## Usage: simple

```hcl
module "groups" {
  source = "../"

  environment = var.environment

  groups = {
    demo = { region = "westeurope" }
  }
}
```

## Resources

| Name | Type |
| :-- | :-- |
| [azurerm_resource_group](https://registry.terraform.io/providers/hashicorp/azurerm/latest/docs/resources/resource_group) | resource |

## Inputs

| Name | Description | Type | Required |
| :-- | :-- | :-- | :-- |
| `groups` | describes resource group related configuration | object | yes |
| `environment` | contains shortname of the environment used for naming convention | string | yes |
| `suffix` | contains the suffix name that can be used for naming convention | string | no |

## Outputs

| Name | Description |
| :-- | :-- |
| `groups` | contains all resource group configuration |

## Authors

Module is maintained by [Dennis Kool](https://github.com/dkooll)

## License

MIT Licensed. See [LICENSE](https://github.com/aztfmods/terraform-azure-rg/blob/main/LICENSE) for full details.
