# -*- mode: ruby -*-
# vi: set ft=ruby :

#Параметры указываются в цикле
Vagrant.configure("2") do |config|
  #Указываем, какую ОС мы будем использовать
  config.vm.box = "ubuntu/focal64"
  config.ssh.insert_key = false
  #Можно указать конкретную версию сборки 
  #Номера сборок можно посмотреть в Vagrant Cloud
  config.vm.box_version = "20220427.0.0"

  #Проброс порта с гостевой машины в хост
  #Порт 80 в созданной ВМ будет доступен нам на порту 8080 хоста
  #config.vm.network "forwarded_port", guest: 80, host: 8080

  #Указываем настройки спецификации ВМ
  #Указывается в отдельном цикле
  config.vm.provider "virtualbox" do |vb|
     # Указываем количество ОЗУ и ядер процессора
     vb.memory = "2048"
     vb.cpus = "2"
  end
  
  #Первоначальная настройка созданной ВМ
  #Установка и запуск Веб-сервера Apache2
  config.vm.provision "shell", inline: <<-SHELL
     sudo apt-get update
     sudo apt-get install -y apache2
     sudo add-apt-repository ppa:cappelikan/ppa
     sudo apt update && sudo apt upgrade -y
     sudo apt install -y mainline
     sudo mainline install-latest
     sudo reboot
  SHELL
end
