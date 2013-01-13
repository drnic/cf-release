Vagrant::Config.run do |config|
  config.vm.box = "bosh-solo-0.6.7"
  downloads = "https://github.com/downloads/drnic/bosh-solo/"
  config.vm.box_url = "#{downloads}bosh-solo-0.6.7.box"

  # config.vm.forward_port 80, 5001
  # config.vm.network :hostonly, "33.33.33.30"

  config.vm.provision :shell, :path => "scripts/vagrant-setup.sh"
  config.vm.customize ["modifyvm", :id, "--memory", 2048]

  if local_bosh_src = ENV['BOSH_SRC']
    config.vm.share_folder "bosh-src", "/bosh", local_bosh_src
  end
end
