# kadNodeExample

A project for integration test kadNode on serveral OS

# HowTo:
prerequirement:
  - install VirtualBox
  - inatall Vagrant
  - install Ansible

cd into subfolder centos or ubuntu

## Start VM and install kadNose from source with ansible
run:
```
 vagrant up --provison
 
 vagrant destroy
```

## The project can import into eclipe workspace using the pom.xml

## Packaging with mavem to buld an target/kadNodeExample-bundle.tar.gz
run:

```
     mvn clean assembly:assembly
```