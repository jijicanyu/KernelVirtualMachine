# KernelVirtualMachine

The KVM module is a full virtualization solution for Linux on x86 hardware containing virtualization extensions (Intel VT or AMD-V). It consists of a loadable kernel module, kvm.ko, that provides the core virtualization infrastructure and a processor specific module, kvm-intel.ko or kvm-amd.ko. 

A loadable Kernel module is an object code that extends the running kernel of an operating system. The LKM usually adds support for new hardware components including file systems and device drivers. If and when the functionality of the LKM is not required, it can be unmounted to free memory and resources.

		-----------------------------
		-			    -
		-	Applications	    -
		-			    -
		-----------------------------
			     ^
			     |
			     |
			     v
		-----------------------------
		-			    -
		-	   Kernel	    -
		-			    -
		-----------------------------
		   ^	     ^		^	
		   |	     |		|
		   v	     v		v
		-------	   -------   --------
		-     -    -     -   -      -
		- CPU -    - Mem -   -Device-
		-     -    -     -   -      -
		-------    -------   --------


Current systems (*-nix) systems and Microsoft Windows add support to the loadable kernel modules even though the names vary (kernel loadable module - kid : Free BSD, kernel extension - kext: macOS and kernelmode driver in Windows.

Using KVM, one can run multiple virtual machines running unmodified Linux or Windows images. Each virtual machine has private virtualized hardware: a network card, disk, graphics adapter.

We are currentlyimplementing functionalities in the linux KVM. KVM is open source software. The kernel component of KVM is included in mainline Linux, as of 2.6.20. The userspace component of KVM is included in mainline QEMU, as of 1.3.

