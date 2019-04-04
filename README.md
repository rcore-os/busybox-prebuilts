busybox-prebuilts
==================================

Prebuilt binaries of busybox for embedded platforms.

## How to build

1. Install [musl toolchain](https://musl.cc) for the corresponding platform, see its README
2. Install libncurses
3. Add the toolchain above to PATH
4. Download and unpack busybox source
5. export `ARCH` and `CROSS_COMPILE` to your platorm (for example, `riscv` and `riscv64-linux-musl`)
6. Run `make defconfig`
7. Run `make menuconfig`, enable static binary, then choose the applets you need
8. Run `make -j${NCPUS}`

You will get `busybox` and `busybox_unstripped` binaries. Put them in corresponding directories.

Verify:

```bash
$ file busybox_unstripped
busybox_unstripped: ELF 64-bit LSB executable, UCB RISC-V, version 1 (SYSV), statically linked, with debug_info, not stripped
```

