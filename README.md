:+1: :sparkles: :camel: :tada: :rocket: :metal: :octocat:
# Vagrant Configuration


<img src="img/Vagrant.png" width="500px" height="200"/>

**Vagrant** is an open-source software product for building and maintaining portable virtual software development environments; e.g., for VirtualBox, KVM, Hyper-V, Docker containers, VMware, and AWS. It tries to simplify the software configuration management of virtualizations in order to increase development productivity. Vagrant is written in the Ruby language, but its ecosystem supports development in a few languages.

**Vagrant** is a tool for building and managing virtual machine environments in a single workflow. With an easy-to-use workflow and focus on automation, Vagrant lowers development environment setup time, increases production parity, and makes the "works on my machine" excuse a relic of the past.

**Step 1:**
Install VirtualBox (latest). https://www.virtualbox.org/wiki/Downloads

**Step 2:**
Install Vagrant (latest). https://www.vagrantup.com/downloads.html

**Step 3:**
Open the cmd and change the directory to C:\HashiCorp\Vagrant\bin>
Then type the following commands:

```bash
C:\HashiCorp\Vagrant\bin> vagrant box add precise32 <provider virtualbox>

C:\HashiCorp\Vagrant\bin> vagrant box add precise32 https://vagrantcloud.com/samdoran/boxes/rhel6
```

<img src="img/box-download.JPG" width="800px"/>

**You can find many boxes on this links:**

 <http://www.vagrantbox.es/>  
 
 <https://app.vagrantup.com/boxes/search>

After successfully adding the BOX for the first time you need to initiate so that the vagrantfile will be created and
you can open this file in notepad & you can customize Hostname, IP Address, ssh ports etc., based on your needs.

```bash
C:\HashiCorp\Vagrant\bin> vagrant init hashicorp/precise32
```
<img src="img/init.JPG" width="600px"/>

**Vagrant file path** ==> C:\HashiCorp\Vagrant\bin\Vagrantfile


After initiation, you can simply run the VM just by command vagrant up 

```bash
C:\HashiCorp\Vagrant\bin> vagrant up
```
<img src="img/vagrant-up.JPG" width="800px"/>

<img src="img/vagrant-up1.JPG" width="800px"/> 

**Step 4:**
Now open the VirtualBox

<img src="img/virtualbox.JPG" width="600px"/> 

**Step 5:**
Now Let's connect to the ubuntu machine by accessing via SSH using putty

Open Putty & enter the following information. I got the IP address of 127.0.0.1 with Port 2222 (**Check "vagrant up" Screentshot**)

**Username:** vagrant

**Password:** vagrant

<img src="img/vagrant-ssh.JPG" width="700px"/> 

---

# Vagrant VmWare Setup

The Vagrant VMware Utility is a system installer package and is required by the Vagrant VMware Desktop plugin for proper functionality. This system installer provides a small utility service that Vagrant utilizes for interacting with VMware on the system

**Step 1:**
Install VmWare Workstation.

**Step 2:**
Install Vagrant VMware Utility (latest). https://www.vagrantup.com/vmware/downloads

**Step 3:**
Vagrant VMware Desktop

The Vagrant VMware Desktop plugin is the Vagrant plugin which adds support for the vmware_desktop provider to Vagrant. The installation method for this plugin follows the same methodology as previous Vagrant VMware plugins

First install the plugin:

```bash
$ vagrant plugin install vagrant-vmware-desktop
```

```diff
- Warning! You cannot use your VMware product license as a Vagrant VMware plugin license.
- They are separate commercial products, each requiring their own license.
```

Then apply the license:

```bash
$ vagrant plugin license vagrant-vmware-desktop ./license.lic
```

To verify the license installation, run:

```bash
$ vagrant
```

**If the license is not installed correctly, you will see an error message.**


Open the cmd and change the directory to C:\HashiCorp\Vagrant\bin>

Then type the following commands:

```bash
C:\HashiCorp\VagrantVMwareUtility\bin> vagrant box add precise64 <provider virtualbox>
```

To get started, create a new Vagrantfile that points to a VMware box

```bash
C:\HashiCorp\VagrantVMwareUtility\bin> vagrant init hashicorp/precise64
```

This will download and bring up a new Workstation virtual machine in Vagrant.

```bash
C:\HashiCorp\VagrantVMwareUtility\bin> vagrant up --provider vmware_workstation
```

---

### Managing the running VM with commands

[VagrantCommand-Line Interface](https://www.vagrantup.com/docs/cli)

```bash
# Check Vagrant Version
$ vagrant -version

# This command lists all the boxes that are installed into Vagrant.
$ vagrant box list

# This command tells you whether or not the box you are using in your current Vagrant environment is outdated.
$ vagrant box outdated

# Boot VM using vagrant
$ vagrant up

# SSH to VM using Vagrant.
$ vagrant ssh

# Suspending the virtual machine.
$ vagrant suspend

# Reload VM settings using Vagrant.
$ vagrant reload

# This resumes a Vagrant managed machine that was previously suspended
$ vagrant resume

# Stop the VM using Vagrant.
$ vagrant halt

# Delete the VM using Vagrant.
$ vagrant destroy
```

### Vagrant File five main parts

VagrantFile Options | Description
------------ | -------------
config.vm.box  | Operating System
config.vm.provider  |  virtualbox
config.vm.network  |  How your host sees you box
config.vm.synced_folder  |  How you access files from your computer
config.vm.provision  |  What we want setup

**For more information please check out the vagrant documentation here:**

<http://www.vagrantbox.es/>

<https://app.terraform.io/session>

![Image of Yaktocat](https://octodex.github.com/images/yaktocat.png)