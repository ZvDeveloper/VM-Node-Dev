Vagrant.configure("2") do |config|

  config.vm.box = "box-cutter/ubuntu1404-desktop"

  # Disable automatic box update checking. If you disable this, then
  # boxes will only be checked for updates when the user runs
  # `vagrant box outdated`. This is not recommended.
  # config.vm.box_check_update = false

  # Create a forwarded port mapping which allows access to a specific port
  # within the machine from a port on the host machine. In the example below,
  # accessing "localhost:8080" will access port 80 on the guest machine.
  # config.vm.network "forwarded_port", guest: 80, host: 8080

  # Create a private network, which allows host-only access to the machine
  # using a specific IP.
  # config.vm.network "private_network", ip: "192.168.33.10"

  # Create a public network, which generally matched to bridged network.
  # Bridged networks make the machine appear as another physical device on
  # your network.
  # config.vm.network "public_network"

  # Share an additional folder to the guest VM. The first argument is
  # the path on the host to the actual folder. The second argument is
  # the path on the guest to mount the folder. And the optional third
  # argument is a set of non-required options.
  # config.vm.synced_folder "../data", "/vagrant_data"

   config.vm.provider "virtualbox" do |vb|
     # Display the VirtualBox GUI when booting the machine
     vb.gui = true

     vb.name = "Ubuntu 1404 - Desenvolvimento"

     # Customize the amount of memory on the VM:
     vb.memory = "3072"
     vb.cpus = 1
   end

  # Define a Vagrant Push strategy for pushing to Atlas. Other push strategies
  # such as FTP and Heroku are also available. See the documentation at
  # https://docs.vagrantup.com/v2/push/atlas.html for more information.
  # config.push.define "atlas" do |push|
  #   push.app = "YOUR_ATLAS_USERNAME/YOUR_APPLICATION_NAME"
  # end

  config.vm.provision "shell", inline: <<-SHELL, privileged: false

      #Git
      sudo apt-get install -y git

      #NVM
      cd /home/vagrant
      wget -qO- https://raw.github.com/creationix/nvm/master/install.sh | sh
      export NVM_DIR="/home/vagrant/.nvm"
      [ -s "$NVM_DIR/nvm.sh" ] && . "$NVM_DIR/nvm.sh"
      nvm install

      #Node.JS
      nvm install 7.6.0
      nvm use 7.6.0
  SHELL

  config.vm.provision "shell", inline: <<-SHELL

      #Google Chrome
      wget -q -O - https://dl-ssl.google.com/linux/linux_signing_key.pub | sudo apt-key add -
      sudo sh -c 'echo "deb [arch=amd64] http://dl.google.com/linux/chrome/deb/ stable main" >> /etc/apt/sources.list.d/google-chrome.list'
      sudo apt-get update
      sudo apt-get install -y google-chrome-stable

      #NPM
      sudo apt-get install -y npm

      #PostgreSQL
      sudo apt-get install -y postgresql pgadmin3

      #MongoDB
      sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv 0C49F3730359A14518585931BC711F9BA15703C6
      echo "deb [ arch=amd64 ] http://repo.mongodb.org/apt/ubuntu trusty/mongodb-org/3.4 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-3.4.list
      sudo apt-get update
      sudo apt-get install -y mongodb-org

      #Visual Studio Code
      wget "https://go.microsoft.com/fwlink/?LinkID=620884" -O vscode.tar.gz
      sudo tar -vzxf vscode.tar.gz -C /opt/
      sudo mv /opt/VSCode*/ /opt/vscode/
      sudo ln -sf /opt/vscode/code /usr/bin/vscode
      echo -e '[Desktop Entry]\n Version=1.0\n Name=vscode\n Exec=/opt/vscode/code --disable-gpu\n Icon=/opt/vscode/resources/app/resources/linux/code.png\n Type=Application\n Categories=Application' | sudo tee /usr/share/applications/vscode.desktop
      sudo chmod +x /usr/share/applications/vscode.desktop
      cp /usr/share/applications/vscode.desktop ~/Desktop

      echo '( Sua máquina está pronta, faça bom proveito! )'
      echo ' --------------------------------------------'
      echo '            o     ^__^ '
      echo '              o   (oo)\________ '
      echo '                  (__)\        )\\\_  '
      echo '                      ||----w | '
      echo '                      ||     || '

  SHELL

end