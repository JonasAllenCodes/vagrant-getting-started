# VAGRANT GETTING STARTED
This is the completed code following along with ["Getting Started"](https://www.vagrantup.com/intro/getting-started/index.html) guide that can be found on the [Vagrant website](https://www.vagrantup.com/).

## Requirements
+ VirtualBox
+ Vagrant

## Instructions
1. Navigate to your folder within the terminal.
1. Run `vagrant box add hashicorp/precise64`, if you do not already have the box added to your machine.
1. Run `vagrant up`, your Vagrant Virtual box is now up and running.

### SSH
Run `vagrant ssh` to connect to the box via ssh. Disconnect by running, `logout` or `exit`.

### Synced Folder
Anything in the project folder will be synced with "/vagrant" on the box. After logging in to the box via SSH, run `ls vagrant`. You will see that the files in the folder of the guest box, reflect what is in the project folder on the host machine. Go ahead and make changes to the files on the host machine or on the guest box. You will see the changes reflected on the other.

### Networking
The guest box network is setup to show up on the host machine via port "4567". You can go to "localhost:4567" or "127.0.0.1:4567" in your browser of the host machine. You will see the files within the project folder hosted. So if you have made no changes to "index.html", you will see "Hello World!" in your browser window. If you did make changes to the file, you see that reflected in your browser.

If you need to change the port number of this guest box on your host machine, open "Vagrantbox" within the project. Go to the line that shows:

```config.vm.network :forwarded_port, guest: 80, host: 4567```

Then change the number "4567" to the port you want to connect to your guest box on your host machine.