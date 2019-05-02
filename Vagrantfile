Vagrant.configure("2") do |config|
  config.vm.box = "generic/arch"
  config.vm.synced_folder "c:/users/pmotard/code", "/home/vagrant/code"
  config.vm.synced_folder "c:/users/pmotard/.ssh", "/home/vagrant/ssh"

  $script = <<-SCRIPT
  sudo pacman -Syyu --noconfirm
  sudo pacman --noconfirm -S git
  git clone https://github.com/kewlfft/ansible-aur.git ~/.ansible/plugins/modules/aur
  sudo pacman --noconfirm -S ansible
  SCRIPT

  config.vm.provision "shell", inline: $script

  config.vm.provision "ansible_local" do |ansible|
    ansible.playbook = "vagrant.yml"
    ansible.provisioning_path = "/home/vagrant/code/dot-ansible"
  end
end