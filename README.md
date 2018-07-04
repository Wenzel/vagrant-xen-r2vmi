# vagrant-xen

This repository provides a set of Vagrant boxes to configure and install Xen.

The initial goal was to build a test suite for virtual machine introspection
tools on Xen in a reproducible environment, but it can be extended to many use
cases revolving around Xen development.

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
