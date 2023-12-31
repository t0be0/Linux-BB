# Linux-BB

Just booting a Linux from kernel and busybox

[+] Building (from script)
--------------------------

	> Takes around 10-30 mins
	
	[*] pre-reqs:
		- for compiling kernel
			- [ fakeroot build-essential ncurses-dev xz-utils libssl-dev/openssl bc flex libelf-dev bison ]
		- emulator
			- QEMU [ qemu-system ]
			
	[*] building:
		- simply run ./build.sh [ ./build.sh ]
			- builds kernel[bzImage] and initrd.img inside /build
			
	[*] kernel-panic:
		- run what u build with ./run.sh [ ./run.sh ]

[+] skip building
-----------------
	
	> already compiled and built kernel, initrd.img (inside /build)
	- skip building and simply run ./run.sh [ ./run.sh ]

[+] Getting more Storage
------------------------

	[*] qemu-img:
		- create a dynamic Disk Storage image
			[ qemu-img create -f <FORMAT> <NAME> <SIZE> ]
			[ qemu-img create -f qcow2 HDA.img 2G ]

	[*] running:
		- simply run ./run.sh with -d <IMG> flag
			[ ./run.sh -d HDA.img ]

	[*] setting up disk:
		- create partition with fdisk [ prolly on /dev/sda ]
		- format using mkfs.ext2 and
		- mount it

[!] To-Do
---------

	- Add more compiled-binaries (especially gcc) maybe
