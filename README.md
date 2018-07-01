# vagrant-xen

This Vagrant box installs the Xen hypervisor to test Virtual Machine Introspection tools.

# requirements

- [Vagrant](https://www.vagrantup.com/)
- `ansible`
- `ruby-dev`
- `libvirt-dev`

# setup

    $ vagrant plugin install vagrant-libvirt
    $ vagrant plugin install vagrant-reload
    $ vagrant up --provider=libvirt
