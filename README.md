# awx-virtualbox-build

Pre-requisites:
  OS: Centos 7 VM using VirtualBox
  Networking Type: Bridge Adapter
  Ansible with basic configuration

If you don't have an ssh key yet in your Ansible hosts run the following and use defaults:
  1. ssh-keygen
  2. Copy your .ssh/id_rsa.pub
  
Target Host:
   Insert the "VirtualBox Guest Addition" under Devices menu
  
On target hosts perform the following as root:
  useradd ansible-security && usermod -G wheel ansible-security && sudo sed --in-place 's/^#\s*\(%wheel\s\+ALL=(ALL)\s\+NOPASSWD:\s\+ALL\)/\1/' /etc/sudoers
  
Run the following as ansible-security from target host:
mkdir .ssh && echo "YOUR SSH KEY HERE" > .ssh/authorized_keys && chmod 400 .ssh/authorized_keys && chmod 500 .ssh/


 
 
