# tf-ob-use-privatemodule-github
Terraform Cloud - Use private module created in Github

### Prerequirements

- Private module published in the Terraform Cloud

### Implementation

- Create main.tf file with following content

```
module "privatemodule" {
  source  = "app.terraform.io/terraform201-ob/privatemodule/null"
  version = "1.0.0"
  resource_number = 10
}
```

- Run the `terraform login` from the current folder to save app.terraform.io token locally

- Run the `terraform apply`

