# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

  config.vm.box = "dkd/solr-typo3-devbox"
  config.vm.box_version = "1.9.0"
  config.vm.network :private_network, ip: "192.168.144.120"

  config.ssh.forward_agent = true

  host = RbConfig::CONFIG['host_os']

  # Use nfs when running on a unix system
  if host =~ /darwin/
	  config.vm.synced_folder ".", "/vagrant", nfs: true
  elsif host =~ /linux/
	  config.vm.synced_folder ".", "/vagrant", nfs: true
  else
	  config.vm.synced_folder ".", "/vagrant", mount_options: ['dmode=777','fmode=666']
  end

  # Assign reasonable memory and cpu cores
  config.vm.provider :virtualbox do |v|
      # Give VM 1/4 system memory & access to all cpu cores on the host
      if host =~ /darwin/
        cpus = `sysctl -n hw.ncpu`.to_i
        # sysctl returns Bytes and we need to convert to MB
        mem = `sysctl -n hw.memsize`.to_i / 1024 / 1024 / 4
      elsif host =~ /linux/
        cpus = `nproc`.to_i
        # meminfo shows KB and we need to convert to MB
        mem = `grep 'MemTotal' /proc/meminfo | sed -e 's/MemTotal://' -e 's/ kB//'`.to_i / 1024 / 4
      else
        cpus = 2
        mem = 4096
      end

      v.customize ["modifyvm", :id, "--memory", mem]
      v.customize ["modifyvm", :id, "--cpus", cpus]
      v.gui = false
  end

end
