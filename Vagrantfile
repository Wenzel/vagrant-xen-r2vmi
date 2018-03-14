Vagrant.configure(2) do |config|
    config.vm.box = "debian/stretch64"

    config.vm.synced_folder "..", "/vagrant",
        :nfs => true,
        :nfs_version => 4,
        :nfs_udp => false

    config.vm.provider :libvirt do |libvirt|
        libvirt.cpus = 2
        libvirt.memory = 3000
        libvirt.nic_model_type = "virtio"
        libvirt.driver = "kvm"
        libvirt.nested = true
    end

    config.vm.provision "ansible" do |ansible|
        ansible.compatibility_mode = "2.0"
        # ansible.verbose =  '-vvv'
        # ansible.start_at_task =  ''
        root_dir = '/vagrant'
        ansible.playbook = "provision/playbook_1.yml"
    end

    config.vm.provision :reload

    config.vm.provision "ansible" do |ansible|
        ansible.compatibility_mode = "2.0"
        # ansible.verbose =  '-vvv'
        # ansible.verbose =  '-vvv'
        # ansible.start_at_task =  ''
        root_dir = '/vagrant'
        ansible.playbook = "provision/playbook_2.yml"
    end
end
