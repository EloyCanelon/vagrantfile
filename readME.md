# VagrantFile for VirtualBox Deployment

## Welcome to this VagragntFile repository!

### This repository contains a Vagrantfile designed to quickly set up a [specify environment type, e.g., "Web Development Environment with Apache, MySQL, and PHP", "for Python and Django", "with Docker and Kubernetes"]. With Vagrant, you can have a consistent and reproducible environment for your project, avoiding "it works on my machine" issues.


## Troubleshooting
Sometimes we can have issues deploying our VM, these are some usuals errors:
'Stderr: VBoxManage: error: VirtualBox can't enable the AMD-V extension. Please disable the KVM kernel extension, recompile your kernel and reboot (VERR_SVM_IN_USE)'

For this we can use the nexts commands: 
'lsmod | grep "kvm"'

If we are getting this stdout:
'
kvm_amd               245760  0
kvm                  1429504  1 kvm_amd
irqbypass              12288  1 kvm
ccp                   159744  1 kvm_amd
'

We use this command to fix the error: 

'sudo modprobe -r kvm_amd'

'sudo modprobe -r kvm' 

### For a complete reference or documentation, please see the online documentation at https://docs.vagrantup.com.