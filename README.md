# kadNodeExample

A project for integration test kadNode on serveral OS

# HowTo:
prerequirement:
  - install VirtualBox
  - inatall Vagrant
  - install Ansible

# Known Bugs
```
fatal: [centos-server.locale]: FAILED! => {"changed": false, 
"msg": "The checksum for /tmp/mbedtls-2.7.0-gpl.tgz did not match 
aeb66d6cd43aa1c79c145d15845c655627a7fc30d624148aaafbb6c36d7f55ef; it was 
6c8e62985c5a73318d391e1327830b3ff85f87a0."}
```

## Start VM and install kadNode from source with ansible
run:
```
 // Start all VM
 vagrant up --provison
 
 // 
 vagrant up --provision ubuntu-server.locale
 
 //
 vagrant ssh ubuntu-server.locale
 
 //
 vagrant up --provision centos-server.locale
 
 //
 vagrant ssh centos-server.locale
 
 //
 vagrant global-status
 
 // Stop all VM
 vagrant halt
 
 //
 vagrant destroy
```

## The project can import into eclipe workspace using the pom.xml

## Packaging with mavem to buld an target/kadNodeExample-bundle.tar.gz
run:

```
     mvn clean assembly:assembly
```