.PHONY: all clean
OUT := out
all: kernel
kernel:
	nasm -o disk.img kernel.asm
qemu:
	qemu-system-i386 -s -soundhw pcspk -fda disk.img
clean:
	rm -rfv -- disk.img

