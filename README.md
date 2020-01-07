#### Install AWX in Centos 7 from scratch the Ansible way

The playbook will build a docker-type AWX from a fresh Centos7 install. Installing AWX is straight forward but there are some caveats that I've encountered along the way that this playbook will ensure you don't get any snags. These issues that I've encountered could be daunting for anyone that lacks experience in Linux. So, I made sure that everything will work from start to finish. 

The fastest way to get this up and running is using Ansible on cygwin if you are using Windows. Just make sure you've got ``python2 python2-devel python27-pip gcc-core libffi-devel libssl1.0-devel git ssh`` packages installed. Then you'll be able to compile ansible in cygwin

#### Pre-requisites:
  * Target Host:
      1. OS: Centos 7 VM using VirtualBox
      2. Bridge Adapter
      3. VirtualBox Guest Addition mounted from Device > Insert Guest Additions CD image menu in Virtualbox
      4. 2 CPU
      5. 6 GB Memory
  * Ansible Host:
      1. Working ansible
      2. Clone this repository: ``git clone https://github.com/banjodocker/awx-virtualbox-build.git``
      3. edit cfg/host 
      4. change the IP address which is your target host

#### NOTES: If you don't have an ssh key yet in your Ansible hosts run the following and use defaults:
  1. ssh-keygen
  2. Copy your .ssh/id_rsa.pub
  

#### Target Host Steps:
Run as root:

```useradd ansible-security && usermod -G wheel ansible-security && sed --in-place 's/^#\s*\(%wheel\s\+ALL=(ALL)\s\+NOPASSWD:\s\+ALL\)/\1/' /etc/sudoers```

Run as ansible-security:

```mkdir .ssh && echo "YOUR SSH KEY HERE" > .ssh/authorized_keys && chmod 400 .ssh/authorized_keys && chmod 500 .ssh/```


 
 
