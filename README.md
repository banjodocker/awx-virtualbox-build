#### AWX installer for Centos 7 from scratch

The playbook will build a docker-type AWX from a fresh Centos7 install. I build this playbook for my team who lacks knowledge on Ansible would appreciate how easy it is to learn Ansible and have a fully working AWX.

#### Pre-requisites:
  * Target Host:
      1. OS: Centos 7 VM using VirtualBox
      2. Bridge Adapter
      3. VirtualBox Guest Addition mounted from Device > Insert Guest Additions CD image menu in Virtualbox
      4. 2 CPU
      5. 6 GB Memory
  * Ansible Host:
      1. Working ansible
      2. Clone this repository
      3. edit cfg/host 
      4. change the IP address which is your target host

#### NOTES: If you don't have an ssh key yet in your Ansible hosts run the following and use defaults:
  1. ssh-keygen
  2. Copy your .ssh/id_rsa.pub
  

#### Target Host Steps:
Run as root:
-  useradd ansible-security && usermod -G wheel ansible-security && sed --in-place 's/^#\s*\(%wheel\s\+ALL=(ALL)\s\+NOPASSWD:\s\+ALL\)/\1/' /etc/sudoers

Run as ansible-security:
-  mkdir .ssh && echo "YOUR SSH KEY HERE" > .ssh/authorized_keys && chmod 400 .ssh/authorized_keys && chmod 500 .ssh/


 
 
