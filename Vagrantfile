Vagrant::Config.run do |config|
  config.vm.box       = 'precise64'
  config.vm.box_url   = 'http://files.vagrantup.com/precise64.box'
  config.vm.host_name = 'rails-dev-box'
  
  config.vm.share_folder "Development", "~/Development", "/Users/film42/Dropbox/Development", :nfs => true

  config.vm.forward_port 3000, 3000
  
  config.vm.customize ["modifyvm", :id, "--memory", "3072"]
  config.vm.customize ["modifyvm", :id, "--cpus", "2"]

  config.vm.provision :puppet,
    :manifests_path => 'puppet/manifests',
    :module_path    => 'puppet/modules'
end
