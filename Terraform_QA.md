1. Data source
2. output block
3. ingone_changes in terrafrom plan
# What is IAC (Infrastructure as code)

![[Pasted image 20220306000057.png]]
# TF architecture?
# How to remove only few resources through terraform ?
`terraform destroy -target aws_instance.web`

## Does Terraform Apply / Plan automatically run Terraform init ?
NO

## What does Terraform apply do?

# What is TF backend ?
Each Terraform configuration can specify a backend, which defines two main things:
-   Where operations are performed 
-   Where the state is stored (Terraform keeps track of all the resources created in a state file)

# What is Null resource?
# What is module?
# Name some builtin provisioners?
- Local-exec
- Remote-exec
- file provisioner

### Explain State File Locking?
State file locking is Terraform mechanism in which operations on a specific state file are blocked to avoid conflicts between multiple users performing the same process. When one user releases the lock, then only the other one can operate on that state. This helps in preventing state file corruption. This is a backend operation.

# What is a Tainted Resource?
A tainted resource is a resource that is forced to be destroyed and recreated on the next apply command. When a resource is marked as tainted, the state files are updated, but nothing changes on infrastructure. The terraform plan out shows that help will get destroyed and recreated. The changes get implemented when the next apply happens.

# How will you upgrade plugins on Terraform?
Run ‘terraform init’ with ‘-upgrade’ option. This command rechecks the releases.hashicorp.com to find new acceptable provider versions. It also downloads available provider versions. “.terraform/plugins/<OS>_<ARCH>” is the automatic downloads directory.

## what are the different ways to pass the arguments?
variables.tfvars
variables.tf
resource block
environment variables
cli arguments

## how to upgrade plugins in terraform ? Ans : terraform init -upgrade

# how to restore terraform state file.