# vagrant-xen-r2vmi

This repository provides a set of Vagrant boxes to configure and install Xen, in order to run the
[r2vmi](https://github.com/Wenzel/r2vmi) `radare2` plugin.

_Note_: Only `fedora` is supported at the moment.

# Requirements

- [Vagrant](https://www.vagrantup.com/)
- `ansible`
- `ruby-dev`
- `libvirt-dev`

# Configuration

A few options can be tweaked in the `<distro>/Vagrantfile`.

- `source`: build Xen from source, or use the distribution packages
- `vmi`: install VMI tools (`libvmi`, `libvmi-python`, `rekall`)

# Setup

Install the required `Vagrant` plugins:

    $ vagrant plugin install vagrant-libvirt vagrant-reload

The choose a supported distribution and build the box:

    $ cd fedora
    $ vagrant up --provider=libvirt

Your `Vagrant` box is ready !

# Usage

Run `vagrant ssh` to get a shell into the VM.

# Virt-Manager: remote connection

As SSH is open for password authentication, you can manage your VMs from
`virt-manager` with a remote connection.

Use `vagrant ssh` and `ip a` to get the IP address of the VM, and add a new
connection in `virt-manager` with these credentials:

- username: `root`
- password: `vagrant`
