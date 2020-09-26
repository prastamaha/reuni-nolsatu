# Vagrant project example

## Prerequisites
1. vagrant installed
2. virtualbox installed
3. clone repository
```
git clone https://github.com/prastamaha/reuni-nolsatu.git
cd reuni-nolsatu
```
4. download box
```
vagrant box add hashicorp/bionic64 https://app.vagrantup.com/hashicorp/boxes/bionic64/versions/1.0.282/providers/virtualbox.box 
```
5. run example
```
cd example1
vagrant up
vagrant status
vagrant ssh
```
6. destroy
```
cd example1
vagrant destroy
```
## Link:
- [vagrant download](https://www.vagrantup.com/downloads.html)
- [vagrant docs](https://www.vagrantup.com/docs)
- [slide reuni nolsatu](https://docs.google.com/presentation/d/1ah_W_fVMs3X6F-bk8-XY38UpWGvBNjjCPU4y70C7zfs/edit?usp=sharing)

### [example1](example1)
- __box__: singlebox (hashicorp/bionic64)
- __provider__: virtualbox (cpu: 2, memory: 2048)
- __network__: private_network (dhcp)

### [example2](example2)
- __box__: singlebox (hashicorp/bionic64)
- __provider__: virtualbox (cpu: 2, memory: 2048)
- __network__: forwarded_port (host: 8080, guest: 80)
- __sync__: host=`~/html` , guest=`/var/www/html`
- __provision__: shell (install nginx)

### [example3](example3)
- __box__: singlebox (hashicorp/bionic64)
- __provider__: virtualbox (cpu: 2, memory: 2048)
- __network__: private_network (10.0.0.10)
- __sync__: host=`~/html` , guest=`/var/www/html`
- __provision__: ansible (install nginx)

### [example4](example4)
- __box__: multi-machine (hashicorp/bionic64)
- __provider__: virtualbox (cpu: 2, memory: 2048)
- __network__: private_network (vm1: 10.0.0.10, vm2: 10.0.0.20)

### [example5](example5)
- __box__: multi-machine (hashicorp/bionic64)
- __provider__: virtualbox (cpu: 2, memory: 2048)
- __network__: private_network (based on `number_of_vm`)
- __plugin__: vagrant-hostmanager

### [example6](example6)
- __box__: multi-machine (hashicorp/bionic64)
- __provision__: ansible (setup kubernetes master with 1 master, N worker)
- __provider__: virtualbox (cpu: 2, memory: 2048)
- __network__: private_network (based on `192.168.50.N`)
