Vagrant::Config.run do |config|
  # All Vagrant configuration is done here. The most common configuration
  # options are documented and commented below. For a complete reference,
  # please see the online documentation at vagrantup.com.

  # Every Vagrant virtual environment requires a box to build off of.
  config.vm.box = "vagrant-natty-amd64-ruby-05-06-2011"

  config.vm.forward_port("web", 80, 8080, :auto => true)
  config.vm.forward_port("mysql", 3306, 3306, :auto => true)
  config.vm.customize do |vm|
    vm.memory_size = 2048
  end

  config.vm.box_url = "http://irulan.homeunix.net/vagrant-natty-amd64-ruby-05-06-2011.box"

  #config.vm.provision :puppet, :module_path => ["example42","modules"] , :manifests_path => "manifests" , :manifest_file => "site.pp", :options => "--debug"
#  config.vm.provision :puppet, :module_path => "modules" , :manifests_path => "manifests" , :manifest_file => "site.pp", :options => "--trace -d"
#  config.vm.provision :puppet, :module_path => "modules" , :manifests_path => "manifests" , :manifest_file => "site.pp"
  config.vm.share_folder "v-data", "/vagrant_data", "data"



  # The url from where the 'config.vm.box' box will be fetched if it
  # doesn't already exist on the user's system.
  # config.vm.box_url = "http://domain.com/path/to/above.box"
  # config.vm.box_url = "http://irulan.homeunix.net/ubuntu-11.04-server-amd64.box"

  # Boot with a GUI so you can see the screen. (Default is headless)
  # config.vm.boot_mode = :gui

  # Assign this VM to a host only network IP, allowing you to access it
  # via the IP.
  # config.vm.network "33.33.33.10"

  # Forward a port from the guest to the host, which allows for outside
  # computers to access the VM, whereas host only networking does not.
  # config.vm.forward_port "http", 80, 8080

  # Share an additional folder to the guest VM. The first argument is
  # an identifier, the second is the path on the guest to mount the
  # folder, and the third is the path on the host to the actual folder.
  # config.vm.share_folder "v-data", "/vagrant_data", "../data"

  # Enable provisioning with Puppet stand alone.  Puppet manifests
  # are contained in a directory path relative to this Vagrantfile.
  # You will need to create the manifests directory and a manifest in
  # the file ubuntu-11.04-server-amd64.pp in the manifests_path directory.
  #
  # An example Puppet manifest to provision the message of the day:
  #
  # # File { owner => 0, group => 0, mode => 0644 }
  # #
  # # file { '/etc/motd':
  # #   content => "Welcome to your Vagrant-built virtual machine!
  # #               Managed by Puppet.\n"
  # # }
  #
  # config.vm.provision :puppet do |puppet|
  #   puppet.manifests_path = "manifests"
  #   puppet.manifest_file  = "ubuntu-11.04-server-amd64.pp"
  # end

  # Enable provisioning with chef solo, specifying a cookbooks path (relative
  # to this Vagrantfile), and adding some recipes and/or roles.  #
  #
  #config.vm.provision :chef_solo do |chef|
  #  chef.cookbooks_path = ["cookbooks"]
  #  chef.roles_path = "roles"
  #  chef.add_role "basic-box"
  #  chef.log_level = :info
  #end

     # You may also specify custom JSON attributes:
  #   chef.json.merge!({ :mysql_password => "foo" })

  # Enable provisioning with chef server, specifying the chef server URL,
  # and the path to the validation key (relative to this Vagrantfile).
  #
  # The Opscode Platform uses HTTPS. Substitute your organization for
  # ORGNAME in the URL and validation key.
  #
  # If you have your own Chef Server, use the appropriate URL, which may be
  # HTTP instead of HTTPS depending on your configuration. Also change the
  # validation key to validation.pem.
  #
  # config.vm.provision :chef_server do |chef|
  #   chef.chef_server_url = "https://api.opscode.com/organizations/ORGNAME"
  #   chef.validation_key_path = "ORGNAME-validator.pem"
  # end
  #
  # If you're using the Opscode platform, your validator client is
  # ORGNAME-validator, replacing ORGNAME with your organization name.
  #
  # IF you have your own Chef Server, the default validation client name is
  # chef-validator, unless you changed the configuration.
  #
  #   chef.validation_client_name = "ORGNAME-validator"
  config.vm.provision :chef_server do |chef|
    chef.node_name = "zorrander"
    chef.chef_server_url = "http://192.168.1.92:4000"
    chef.validation_key_path = "zorrander.pem"
  end
end
