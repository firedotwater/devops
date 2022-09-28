# nginx-task

In this task we should run a vagrant file with the nginx webserver and port forwarding from 80:8'0 to 8080:8080.
We had to use a provision file to update, upgrade and install the service.


## Vagrant file


This was the vagrant final file. It contains the vm box, hostname, port forwarding and the necessary network settings.

```
Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/xenial64"
  config.vm.hostname = "web-dev-fab"
  config.vm.provision "shell", path: "provision.sh"
  config.vm.network "forwarded_port", guest: 80, host: 8080, id: "nginx-cnt"
```


## provision.sh

In this provision file we specified which service and updates we want to install and we can remove the var/www link and add a new one to attach the right files.


 
