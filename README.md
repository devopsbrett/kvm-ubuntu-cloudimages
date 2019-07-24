# Ubuntu Cloud Images for KVM

## What?

This repository is a staging area for my experiments in creating automated builds of ubuntu cloud images for use with KVM. 

## Why?

When using a hypervisor cloud images are a massive time saver, not having to go through the process of installing an operating system each time you want to spin up a new VM. [Ubuntu provide cloud images](http://cloud-images.ubuntu.com), and up until recently were more than sufficient for my needs, and provisioned as follows:

1. Create cloud-init script
2. Provision VM from cloud image
3. Wait for provision
4. USE!

Recently, however, I've noticed that there are a large number of packages that are installed during the cloud-init run that are common across all my VMs. Moving these packages away from the cloud-init script and into the cloud image itself would speed up the provisioning of each new VM. Packer is a great tool for this, however getting it to play nicely, using an existing ubuntu cloud image as the base has been a black hole of enormous pain. This is something I know I'm never going to want to go through again so I will be documenting all progress made along with examples here.

