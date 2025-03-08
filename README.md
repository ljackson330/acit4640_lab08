# 4640-w9-lab

# Intro

Complete the configuration files as shown in this repo to define your Packer image and deploy it using Terraform.

Use the provided script to upload your SSH key.

# Commands

CD into the ``packer/`` directory.

First, (after completing the Packer config), initialize the Packer project.

``packer init .``

This will install all required plugins. Then, validate the config file.

``packer validate .``

This will ensure the config is valid and point out any issues.

Build the Packer image:

``packer build .``

CD into the ``terraform/`` directory.

Initialize the Terraform project:

``terraform init``

This will install all required providers.

Validate your config:

``terraform validate``

Do a dry run with terraform plan to review the changes before making them:

``terraform plan -out=tfplan``

Review it and make sure it looks good, then launch the infrastructure:

``terraform apply``

Clean up with:

``terraform destroy``

Deregister the AMI:

``aws ec2 describe-images --owners self --query "Images[].[ImageId,Name]" --output table``

Take the AMI ID from that command and enter it here:

``aws ec2 deregister-image --image-id <ami-id>``
