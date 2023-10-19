


Vagrant.configure("2") do |config|
  # Utilisez la box Ubuntu 22.04
  config.vm.box = "generic/ubuntu2204"
  config.vm.box_version = "4.3.2"

  # Configuration de la machine virtuelle
  config.vm.network "private_network", type: "dhcp"
  config.vm.provider "virtualbox" do |vb|
    vb.memory = 1024  # Définissez la mémoire de la machine virtuelle selon vos besoins
    vb.cpus = 1      # Définissez le nombre de CPU selon vos besoins
  end

  # Configuration de la provision
  config.vm.provision "shell", inline: <<-SHELL
    # Mettre à jour la liste des paquets et effectuer les mises à jour du système
    sudo apt-get update
    sudo apt-get upgrade -y

    # Installer Nginx
    sudo apt-get install -y nginx

    # Installer MariaDB et définir le mot de passe root
    sudo debconf-set-selections <<< 'mariadb-server-10.5 mysql-server/root_password password Abcdef'
    sudo debconf-set-selections <<< 'mariadb-server-10.5 mysql-server/root_password_again password Abcdef'
    sudo apt-get install -y mariadb-server mariadb-client

    # Installer PHP 8.0 et les extensions PHP courantes
    sudo apt-get install -y software-properties-common
    sudo add-apt-repository ppa:ondrej/php
    sudo apt-get update
    sudo apt-get install -y php8.0 php8.0-fpm php8.0-mysql php8.0-common php8.0-gd php8.0-cli php8.0-curl php8.0-zip php8.0-json php8.0-opcache

    # Redémarrer les services
    sudo systemctl restart nginx
    sudo systemctl restart php8.0-fpm

    # Installation de wordpress
    cd /var/www/html
    sudo wget https://wordpress.org/latest.tar.gz
    sudo tar -xzvf latest.tar.gz
    sudo mv wordpress/* .
    sudo rm -rf wordpress
    sudo chown -R www-data:www-data /var/www/html

    mysql -u root -pAbcdef -e "CREATE DATABASE wordpress;"
    mysql -u root -pAbcdef -e "CREATE USER 'wordpressuser'@'localhost' IDENTIFIED BY 'Abcdef';"
    mysql -u root -pAbcdef -e "GRANT ALL PRIVILEGES ON wordpress.* TO 'wordpressuser'@'localhost';"
    mysql -u root -pAbcdef -e "FLUSH PRIVILEGES;"

  SHELL
end