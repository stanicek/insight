# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure(2) do |config|
  # The most common configuration options are documented and commented below.
  # For a complete reference, please see the online documentation at
  # https://docs.vagrantup.com.
  config.vm.define "insight" do |insight|
    insight.vm.box = "hashicorp/precise64"
    insight.vm.provision :shell, name: "setup", path: "bootstrap.sh"
    insight.vm.network :forwarded_port, guest: 80, host: 8888
    insight.ssh.shell = "bash -c 'BASH_ENV=/etc/profile exec bash'"
    insight.vm.post_up_message = "Welcome to Project Insight 2016. Visit 'http://127.0.0.1:8888' in your browser to begin.\n" +
      "To begin the test go to 'http://127.0.0.1:8888/users/add' in your browser."
  end
end
