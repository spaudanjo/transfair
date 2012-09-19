Transfair
=========

This is the repository of the lean approach to a webapp for Transfair.

Read more about Transfair on  http://www.transfair.co/


About Vagrant (makes the development start easily)
=========

Vagrant is for creating and configuring lightweight, reproducible and portable development environments. It lowers development environment setup time, maximizes dev/prod parity, and makes the "works on my machine" excuse a relic of the past.
* see the project-website here: http://vagrantup.com/
* and this excelent introduction-video (one of Ryan Bates popular RailsCasts) here: http://railscasts.com/episodes/292-virtual-machines-with-vagrant

The short version of the usage:
* make sure Virtual Box is installed (can be downloaded here: http://www.virtualbox.org/)
* make sure the Vagrant gem is installed. Calling 'bundle' inside of the transfair-project-folder should take care of that.
* call 'vagrant up' from within the transfair-project-folder. With this command you start a Vagrant virtual machine. The first time doing so, it will need a while, because it needs to download the box-file and configuring it a bit.
* now the virtual box is running and you can connect to it through ssh via the command 'vagrant ssh'
* after connecting via ssh, you should go to the rails-project-folder via 'cd /vagrant' (this folder is a shared folder between your host machine and the virtual machine, so whenever you edit an source-file of your Rails app from within your host-machine, it is instantly updated in the virtual machine as well).
* here you should work with the app-directory as you are probably used to be, like running 'bundle', 'rake db:migrate' and so on and finally 'rails s' (the default port of 3000 will be forwarded from the host machine to the virtual machine so that you can test the webapp from your browser of your host machine directly).

Transfair has its own preconfigured Virtual Box file, which is (currently) stored at Amazon S3 ("https://s3-eu-west-1.amazonaws.com/transfair-vagrant-images/transfair-ubuntu-postgresql.box") and on which is regarded inside of the Vagrantfile.
