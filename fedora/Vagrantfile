Vagrant.configure(2) do |config|
    config.vm.box = "fedora/28-cloud-base"

    config.vm.synced_folder ".", "/vagrant", disabled: true

    config.vm.provider :libvirt do |libvirt|
        libvirt.cpus = 2
        libvirt.memory = 4096
        libvirt.nic_model_type = "virtio"
        libvirt.driver = "kvm"
        libvirt.nested = true
        libvirt.machine_virtual_size = 40
    end

    config.vm.provision "ansible" do |ansible|
        ansible.compatibility_mode = "2.0"
        # ansible.verbose =  '-vvv'
        # ansible.start_at_task =  ''
        ansible.playbook = "provision/playbook_1.yml"
    end

    config.vm.provision :reload

    config.vm.provision "ansible" do |ansible|
        ansible.compatibility_mode = "2.0"
        # ansible.verbose =  '-vvv'
        # ansible.start_at_task =  ''
        ansible.playbook = "provision/playbook_2.yml"
    end
end
