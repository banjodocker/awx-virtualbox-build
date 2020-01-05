## AWX Operator VirtualBox Build

Credits to: Jeff Geerling

URL: https://www.jeffgeerling.com/blog/2019/run-ansible-tower-or-awx-kubernetes-or-openshift-tower-operator

## Pre-requisites:
  * Target Host:
      1. OS: Centos 7 VM using VirtualBox
      2. Bridge Adapter
      3. VirtualBox Guest Addition mounted
      4. 2 CPU
      5. 6 GB Memory
  * Ansible Host:
      1. Working ansible host

## NOTES: If you don't have an ssh key yet in your Ansible hosts run the following and use defaults:
  1. ssh-keygen
  2. Copy your .ssh/id_rsa.pub
  

## Target Host Steps:
Run:
-  useradd ansible-security && usermod -G wheel ansible-security && sudo sed --in-place 's/^#\s*\(%wheel\s\+ALL=(ALL)\s\+NOPASSWD:\s\+ALL\)/\1/' /etc/sudoers
-  mkdir .ssh && echo "YOUR SSH KEY HERE" > .ssh/authorized_keys && chmod 400 .ssh/authorized_keys && chmod 500 .ssh/


 
 
