# vagrant-env

A vagrant environment for CIT 595.  This environment has all the course requisite applications needed to succeed as an operating systems programmer student.

## Setup

Install the latest version of [Vagrant](https://www.vagrantup.com/downloads) and [VirtualBox](https://www.virtualbox.org/wiki/downloads).

From the host machine, run
```bash
vagrant up
```
to start the virtual machine and provision according to this vagrantfile

To access the VM, run
```bash
vagrant ssh
```
If successful, the terminal prompt should be `vagrant@cit595Dev:~$`. `logout` will continue to run the VM but return the terminal to the host machine.

## Basic commands
```bash
vagrant suspend
```
will save the state of the VM and pause it.  This returns host machine CPU cycles to the host, but the VM is still stored in memory.  This is similar to hibernating a computer.

```bash
vagrant halt
```
will gracefully shutdown the VM.  This will return the CPU and associated memory to the host machine.  This is similar to safely powering off a computer.

```bash
vagrant destroy
```
completely obliterates all traces of the VM from the host machine.  Not recommended if there are important files saved on the VM (i.e. unpushed projects).  Requires another round of `vagrant up` to re-provision the VM.

## Shared directory

The host machine will attempt to mount the install directory into the VM at `../../vagrant`.  Files saved here will be accessible to the host machine and vice versa.
