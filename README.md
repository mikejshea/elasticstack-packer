## Dashboard VirtualBox

### Install Packer
Packer is a small go app, that really does not require installing. For this project, I put the executable in my folder with all the packer files. You will need to adjust accordingly.

https://www.packer.io/

### CentOS 7 - 1708
Download the 1708 iso build of CentOS-7 Minimal and put is somewhere you can easily access it.

http://isoredirect.centos.org/centos/7/isos/x86_64/CentOS-7-x86_64-Minimal-1708.iso

### Update variables
In the centos-iso-vbox folder you will need to update the ```vars.json``` file to relect your specific needs.

### Create VM
From the centos-iso-vbox, use the command below to run the packer install.
```
packer build --var-file vars.json --force base.json
```
The --force will delete any old virtual machines sitting in the destination folder.

Building the VM can take quite a while.

### Post install
1.  In VirtualBox, import the new appliance.
1.  Start the new virtual machine.
1.  Login with ```root / dashboard```.
1.  In the ```/root``` folder, execute ```./post_install.sh```
1.  Modify the files as instructed.
1.  In the ```/root``` folder, execute ```./stack_restart.sh```
