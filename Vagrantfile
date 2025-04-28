Vagrant.configure("2") do |config|
  # Define Minikube VM
  config.vm.define "minikube" do |minikube|
    # VM configuration
    minikube.vm.box = "easytrainingfr/centos7"
    minikube.vm.network "private_network", type: "static", ip: "192.168.56.10"
    minikube.vm.hostname = "minikube"

    # Remettre le dossier partagé sans erreur
    minikube.vm.synced_folder ".", "/vagrant"

    # VirtualBox provider settings
    minikube.vm.provider "virtualbox" do |v|
      v.name = "minikube"
      v.memory = 4096
      v.cpus = 2
    end

    # Provisioning script
    minikube.vm.provision "shell", path: "install_minikube.sh", env: { 'ENABLE_ZSH' => ENV['ENABLE_ZSH'] }
  end
end
