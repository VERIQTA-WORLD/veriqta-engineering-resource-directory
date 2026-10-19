# Virtualization and Virtual Machines

Study the host, guest, disk, and network boundaries that a VM exercise depends on.

## Understand the guest environment

| Open | What you can find | Access |
| --- | --- | --- |
| [Operating Systems: Three Easy Pieces](https://pages.cs.wisc.edu/~remzi/OSTEP/) | Study operating-system concepts with free chapters and associated exercises. | Free online textbook |
| [UNIX and Linux System Administration Handbook](https://www.admin.com/) | The authors’ site for a broad administration reference; choose relevant chapters and confirm current platform details. | Paid book; author resources |
| [FreeBSD Handbook](https://docs.freebsd.org/en/books/handbook/) | Read the relevant storage, networking, service, or installation chapter alongside a FreeBSD lab. | Free online handbook |
| [FOSDEM video archive](https://video.fosdem.org/) | Discover recorded open-source talks by year and developer room. | Free recording archive |

## Focused references

**[QEMU system emulation →](https://www.qemu.org/docs/master/system/)**  
Choose the machine, device, and launch reference matching your guest.  
**Free reference; host and guest-image requirements**

**[libvirt domain XML →](https://libvirt.org/formatdomain.html)**  
Read the definition behind a virtual machine’s disks and interfaces.  
**Free reference; virtualization familiarity helpful**

## Follow the tools

[QEMU](../04-tools-and-technologies/qemu.md) · [KVM](../04-tools-and-technologies/kvm.md) · [libvirt](../04-tools-and-technologies/libvirt.md) · [Proxmox VE](../04-tools-and-technologies/proxmox.md) · [Hyper-V](../04-tools-and-technologies/hyper-v.md)

## Put one idea to work

Create a disposable guest and map its devices and connectivity to host resources before deleting it. Use the selected guide’s prerequisites and verification steps. Choose an owned or provided learning environment, keep sensitive data out of your notes, and remove the exercise resources when finished.

[Browse this collection](README.md) · [Directory homepage](../README.md)
