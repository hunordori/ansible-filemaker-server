# Install FileMaker Server on Linux

## Main purpose
This playbook installs FileMaker Server on Linux with the Assisted Installer.txt file.

Tested with Ubuntu 22.04 LTS

## Features
- copies the Filemaker Server installer
- creates the Assisted Installer.txt file for automated installation
- installs the necessary dependencies
- installs Filemaker Server
- installs Filemaker Server license Certificate
- mounts SMB shares

# Steps

1. Make sure you have Ansible connection to the target machine.
(You can create an inventory file in the same directory as the playbook)
2. Gather the the following files and place it under the /files directory:
  - Filemaker Server installer (for example: fms_21.1.5.500_Ubuntu22_amd64.zip)
  - Filemaker license Certificate (LicenseCert.fmcert)
3. Make copy of fms_vars.yml.sample and place it under the /vars directory. (filename: fms_vars.yml)
(You can add more variables to the fms_vars.yml file to override default values from defaults/main.yml)
4. (optional) Make a copy of smb_shares.yml.sample (filename: smb_shares.yml)
5. Run the playbook using the following command:
  ansible-playbook -i inventory.yml main.yml
