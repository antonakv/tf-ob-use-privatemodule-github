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

- When running the code with Terraform CLI configure credentials in .terraformrc or terraform.rc to access this module

```
credentials "app.terraform.io" {
  # valid user API token:
  token = "xxxxxx.atlasv1.zzzzzzzzzzzzz"
}
```

- Run the `terraform apply`

