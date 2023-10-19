1. install terraform

2. make a `main.tf`

3. ```
   resource "null_resource" "example" {
     provisioner "local-exec" {
       command = "echo Hello, World"
     }
   }
   ```

4. run `terraform init`

   ```
   Initializing the backend...

   Initializing provider plugins...

   - Finding latest version of hashicorp/null...
   - Installing hashicorp/null v3.2.1...
   - Installed hashicorp/null v3.2.1 (signed by HashiCorp)

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

5. `terraform plan`

   ```
   Terraform used the selected providers to generate the following execution plan. Resource actions are indicated with the following symbols:
    + create

   Terraform will perform the following actions:

   # null_resource.example will be created
   + resource "null_resource" "example" {
     + id = (known after apply)
   }

   Plan: 1 to add, 0 to change, 0 to destroy.

   ───────────────────────────────────────────────

   Note: You didn't use the -out option to save this plan, so Terraform can't guarantee to take exactly these actions if you run "terraform apply" now.

   ```

6. `terraform apply`

   ```
   Terraform used the selected providers to generate the following execution plan. Resource actions are indicated with the following symbols:
     + create

   Terraform will perform the following actions:

     # null_resource.example will be created
     + resource "null_resource" "example" {
         + id = (known after apply)
       }

   Plan: 1 to add, 0 to change, 0 to destroy.

   Do you want to perform these actions?
     Terraform will perform the actions described above.
     Only 'yes' will be accepted to approve.

     Enter a value: yes

   null_resource.example: Creating...
   null_resource.example: Provisioning with 'local-exec'...
   null_resource.example (local-exec): Executing: ["cmd" "/C" "echo Hello, World"]
   null_resource.example (local-exec): Hello, World
   null_resource.example: Creation complete after 0s [id=3808907538124713944]

   Apply complete! Resources: 1 added, 0 changed, 0 destroyed.
   ```
