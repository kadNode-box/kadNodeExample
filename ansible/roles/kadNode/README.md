# kadNode role

this role will install kadNode from source on CentOS server.

sudo apt-get install vagrant ansible
sudo apt-get remove vagrant ansible

Entfernen von ansible (2.3.1.0+dfsg-2) ...
Entfernen von vagrant (1.9.1+dfsg-1) ...


sudo apt-get update
sudo apt-get install software-properties-common
sudo apt-add-repository ppa:ansible/ansible
sudo apt-get update
sudo apt-get install ansible

https://www.vagrantup.com/downloads.html


run: vagrant box add --provider virtualbox --box-version 0.0.11 --insecure https://atlas.hashicorp.com/xxx/boxes/xxx

run: vagrant up --provision


