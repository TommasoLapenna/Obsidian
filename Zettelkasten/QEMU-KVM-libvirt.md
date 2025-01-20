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
