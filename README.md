busybox-riscv-prebuilts
==================================

Prebuilt binaries of busybox for RISC-V.

## How to build

1. Install [riscv-musl-toolchain](jiegec/musl-riscv-toolchain), see its README
2. Install ncurses
3. Add the toolchain above to PATH
4. Download and unpack busybox source
5. Run `ARCH=riscv CROSS_COMPILE=riscv64-linux-musl- make defconfig`
6. Enter `ARCH=riscv CROSS_COMPILE=riscv64-linux-musl- make menuconfig`, enable static binary
7. Run `ARCH=riscv CROSS_COMPILE=riscv64-linux-musl- make -j${NCPUS}`

You will get `busybox` and `busybox_unstripped` binaries. Put them in corresponding directories.

Verify:

```bash
$ file busybox_unstripped
busybox_unstripped: ELF 64-bit LSB executable, UCB RISC-V, version 1 (SYSV), statically linked, with debug_info, not stripped
```

