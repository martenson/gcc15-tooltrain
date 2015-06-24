VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "planemo"
  config.vm.box_url = "https://images.galaxyproject.org/planemo/latest.box"
  config.ssh.username = "ubuntu"

  # Forward nginx and tool shed.
  config.vm.network "forwarded_port", guest: 80, host: 8010
  config.vm.network "forwarded_port", guest: 9009, host: 9009

  # Disable default mount and mount pwd to /opt/galaxy/tools instead.
  config.vm.synced_folder ".", "/vagrant", disabled: true
  config.vm.synced_folder ".", "/opt/galaxy/tools", owner: "vagrant"

end
