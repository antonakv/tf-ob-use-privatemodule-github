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

- Run the `terraform init`

Expected result:

```
% terraform init 
Initializing modules...
Downloading app.terraform.io/terraform201-ob/privatemodule/null 1.0.0 for privatemodule...
- privatemodule in .terraform/modules/privatemodule

Initializing the backend...

Initializing provider plugins...
- Finding hashicorp/null versions matching "~> 3.1.1"...
- Installing hashicorp/null v3.1.1...
- Installed hashicorp/null v3.1.1 (signed by HashiCorp)

Terraform has created a lock file .terraform.lock.hcl to record the provider
selections it made above. Include this file in your version control repository
so that Terraform can guarantee to make the same selections by default when
you run "terraform init" in the future.

Terraform has been successfully initialized!

You may now begin working with Terraform. Try running "terraform plan" to see
any changes that are required for your infrastructure. All Terraform commands
should now work.

If you ever set or change modules or backend configuration for Terraform,
rerun this command to reinitialize your working directory. If you forget, other
commands will detect it and remind you to do so if necessary.
```

- Run the `terraform apply`

Expected result:

```
% terraform apply                                     

Terraform used the selected providers to generate the following execution plan. Resource actions are indicated with the following symbols:
  + create

Terraform will perform the following actions:

  # module.privatemodule.null_resource.mynull[0] will be created
  + resource "null_resource" "mynull" {
      + id = (known after apply)
    }

  # module.privatemodule.null_resource.mynull[1] will be created
  + resource "null_resource" "mynull" {
      + id = (known after apply)
    }

  # module.privatemodule.null_resource.mynull[2] will be created
  + resource "null_resource" "mynull" {
      + id = (known after apply)
    }

  # module.privatemodule.null_resource.mynull[3] will be created
  + resource "null_resource" "mynull" {
      + id = (known after apply)
    }

  # module.privatemodule.null_resource.mynull[4] will be created
  + resource "null_resource" "mynull" {
      + id = (known after apply)
    }

  # module.privatemodule.null_resource.mynull[5] will be created
  + resource "null_resource" "mynull" {
      + id = (known after apply)
    }

  # module.privatemodule.null_resource.mynull[6] will be created
  + resource "null_resource" "mynull" {
      + id = (known after apply)
    }

  # module.privatemodule.null_resource.mynull[7] will be created
  + resource "null_resource" "mynull" {
      + id = (known after apply)
    }

  # module.privatemodule.null_resource.mynull[8] will be created
  + resource "null_resource" "mynull" {
      + id = (known after apply)
    }

  # module.privatemodule.null_resource.mynull[9] will be created
  + resource "null_resource" "mynull" {
      + id = (known after apply)
    }

Plan: 10 to add, 0 to change, 0 to destroy.

Do you want to perform these actions?
  Terraform will perform the actions described above.
  Only 'yes' will be accepted to approve.

  Enter a value: yes

module.privatemodule.null_resource.mynull[6]: Creating...
module.privatemodule.null_resource.mynull[2]: Creating...
module.privatemodule.null_resource.mynull[8]: Creating...
module.privatemodule.null_resource.mynull[4]: Creating...
module.privatemodule.null_resource.mynull[7]: Creating...
module.privatemodule.null_resource.mynull[3]: Creating...
module.privatemodule.null_resource.mynull[9]: Creating...
module.privatemodule.null_resource.mynull[0]: Creating...
module.privatemodule.null_resource.mynull[5]: Creating...
module.privatemodule.null_resource.mynull[1]: Creating...
module.privatemodule.null_resource.mynull[4]: Creation complete after 0s [id=6650301448948167921]
module.privatemodule.null_resource.mynull[1]: Creation complete after 0s [id=2295494467262368708]
module.privatemodule.null_resource.mynull[9]: Creation complete after 0s [id=6007131977130512580]
module.privatemodule.null_resource.mynull[3]: Creation complete after 0s [id=5081892057833835069]
module.privatemodule.null_resource.mynull[8]: Creation complete after 0s [id=2304474468038781413]
module.privatemodule.null_resource.mynull[5]: Creation complete after 0s [id=2004701383229105361]
module.privatemodule.null_resource.mynull[6]: Creation complete after 0s [id=1886285099083736223]
module.privatemodule.null_resource.mynull[7]: Creation complete after 0s [id=4438817766580765607]
module.privatemodule.null_resource.mynull[0]: Creation complete after 0s [id=2121280020405390294]
module.privatemodule.null_resource.mynull[2]: Creation complete after 0s [id=4269116294601065259]

Apply complete! Resources: 10 added, 0 changed, 0 destroyed.
```

