# Unraid

## SSH
### Connect
Connect using ssh and the host or user and host if not the same as the current user ie, `ssh host` or `ssh user@host`
Connect: `ssh root@<ip address of unraid server>`  

Disconnect: `exit`  

### Reboot
To reboot the unraid server: `powerdown -r`  

### Shutdown
To shutdown the unraid server: `powerdown`  

## VM
Manage vms with the virsh program from redhat, can run it with `virsh` then use `help` to get more info about commands ie `help list`
### Start
`virsh start <domain>`

### Shutdown
`virsh shutdown <domain>`

### List VMs (Domains)
`virsh list --all`

### Info
To view details about a particular vm, `virsh dominfo <domain>`

### EFI
The efi's for the virtual machines are located `/etc/libvirt/qemu/nvram/`

### Export
To export a virtual machine make a copy of the vdisk and the settings as an xml file.
1. Vdisks are generally located `/mnt/user/domains/<domain>/vdisk1.img`
2. Virtual machine settings, navigate to the virtual machine's setting page in the web ui `http://tower/VMs/UpdateVM?uuid=<vm uuid>`, use the pill option to view the settings as xml and make a copy.

### Import
1. Create virtual machine through unraid web ui for the same OS type as the vm to be imported
2. Update the xml settings for the vm, with the backup of from the exported vm. 
    - Make sure that `nvram` still points to the efi for the newly created vm.
    - Make sure that the disk points to the vdisk to be imported ie `/mnt/user/domains/<domain to import>/vdisk1.img`
3. Boot the virtual machine