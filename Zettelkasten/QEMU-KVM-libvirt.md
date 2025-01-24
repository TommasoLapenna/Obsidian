Tags: [[Virtualization]] 
# QEMU
QEMU is a generic machine emulator and virtualizer that uses dynamic binary translation. When the mode used is the latter, QEMU can achive near native performance by executing the guest code directly on the host CPU.
# KVM
Kernel-based Virtual Machine is a virtualization technology for Linux. It can function as a hypervisor that runs multiple, isolated VMs. 
An hypervisor is also referred as a Virtual Machine Monitor, its job is by acting as the host, to allocate the necessaries resources to the guests VMs.
# libvirt
Libvirt is an API, deamon and management tool for virtualization platforms. It can enemurate, monitor and use the resources on the managed node
# QEMU + KVM + libvirt
Starting from the bottom:
- KVM accellerates x86/amd64 virtualization, it acts as a shortchut that the guest can use so that it can use the host CPU at almost hardware speed
- QEMU is the virtualizer software that actually runs the VMs, and by using KVM it can "skip" the simulation of the CPU
- libvirt arranges and manages QEMU sessions, its disks and networks
![[virt 1.png]]
# Usage
https://wiki.archlinux.org/title/KVM
https://wiki.archlinux.org/title/QEMU
https://wiki.archlinux.org/title/Libvirt
https://gist.github.com/tatumroaquin/c6464e1ccaef40fd098a4f31db61ab22

- `LC_ALL=C.UTF-8 lscpu | grep Virtualization` hardware virtualization support
- `zgrep CONFIG_KVM= /proc/config.gz` to check if the necessary modules are available in the kernel, it is available if the command returns either 
- `qemu-full qemu-img libvirt virt-install virt-manager virt-viewer edk2-ovmf dnsmasq swtpm guestfs-tools libosinfo tuned` packages
- `sudo systemctl enable libvirtd.service`
- `sudo virt-host-validate qemu` to check if everything works correctly
- `sudo systemctl enable --now tuned.service` to enable TuneD deamon
	- `tuned-adm active` to check the active profile, `tuned-adm list`, to list all the profiles, `sudo tuned-adm profile virtual-host` to set a profile
- libvirt can run either in `session` or `system` mode
	- `sudo virsh uri` to check the current mode
	- `sudo usermod -aG libvirt $USER` to add the current user to the libvirt group
	- `echo 'export LIBVIRT_DEFAULT_URI="qemu:///system"' >> ~/.bashrc sudo virsh uri` to set env variable with the libvirt group
- `sudo getfacl /var/lib/libvirt/images` to check permission on the images directory
	- `sudo setfacl -R -b /var/lib/libvirt/images/` to recursively remove existing ACL permissions, `sudo setfacl -R -m "u:${USER}:rwX" /var/lib/libvirt/images/` to recursively grant permission to the current user, `sudo setfacl -m "d:u:${USER}:rwx" /var/lib/libvirt/images/` to enable special permission default ACL
	- `sudo getfacl /var/lib/libvirt/images/` to check ACL permission within the images directory
# VM Setup
- `qemu-img create -f qcow2 winxp.img 3G` to create a qcow2 of a specified size or  `qemu-img create -f raw image_file 4G` for a raw disk image (qcow2 = flexibility, raw = performance)
- `qemu-system-x86_64 -cdrom iso_image -boot order=d -drive file=disk_image,format=raw` to boot off an ISO image and giving it a specified amount of RAM
- `qemu-system-x86_64 -m 256 -hda winxp.img -cdrom winxpsp2.iso -enable-kvm` to start QEMU with KVM
- `qemu-system-x86_64 options disk_image` to run the virtualized system, to enable KVM append `-accell kvm` withthe `-machine` option