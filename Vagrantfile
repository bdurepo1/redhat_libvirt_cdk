# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|

  # Example configuration of new VM..
  # 
  config.vm.box = "rhel"
  config.vm.define :rhel do |rhel|
    # Box name
    #
   rhel.vm.box = "rhel"

    # Domain Specific Options
    #
    # See README for more info.
    #
    rhel.vm.provider :libvirt do |domain|
      domain.memory = 4096
      domain.cpus = 4
      domain.nested = true
    end

    # Interfaces for VM
    # 
    # Networking features in the form of `config.vm.network`
    #
    #rhel.vm.network :private_network, :ip => '10.20.30.40'
    #rhel.vm.network :public_network, :ip => '10.20.30.41'
  end

  # Options for libvirt vagrant provider.
  config.vm.provider :libvirt do |libvirt|

    # A hypervisor name to access. Different drivers can be specified, but
    # this version of provider creates KVM machines only. Some examples of
    # drivers are kvm (qemu hardware accelerated), qemu (qemu emulated),
    # xen (Xen hypervisor), lxc (Linux Containers),
    # esx (VMware ESX), vmwarews (VMware Workstation) and more. Refer to
    # documentation for available drivers (http://libvirt.org/drivers.html).
    libvirt.driver = "kvm"

    # The name of the server, where libvirtd is running.
    # libvirt.host = "localhost"

    # If use ssh tunnel to connect to Libvirt.
    # libvirt.connect_via_ssh = 

    # The username and password to access Libvirt. Password is not used when
    # connecting via ssh.
    # libvirt.username = "root"
    # libvirt.password = "secret"

    # Libvirt storage pool name, where box image and instance snapshots will
    # be stored.
    # libvirt.storage_pool_name = "default"

    # Set a prefix for the machines that's different than the project dir name.
    #libvirt.default_prefix = ''
  end
end

