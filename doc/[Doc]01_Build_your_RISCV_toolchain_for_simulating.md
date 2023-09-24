# Build your RISCV toolchain for simulating

Help you build `qemu-system-riscv64` command and run a Linux demo.

Host Machine Arch
------------------
- `Mac M1 Pro` with AArch64 arch

Build toolchain for RISCV
-------------------------
## Use `brew` tool

## Manually compilation (Recommonded)
Reference to `https://github.com/riscv-collab/riscv-gnu-toolchain`

**Warning**: git clone takes around 6.65 GB of disk and download size
```shell
## Getting the source
git clone --recursive https://github.com/riscv/riscv-gnu-toolchain
cd risv-gnu-toolchain
mkdir build
cd $_
../configure --prefix=$(pwd)
make -j10
```

Build Qemu 8.1.1 [TODO: Not finished]
----------
1. Get the qemu source code.
```shell
wget  https://download.qemu.org/qemu-8.1.1.tar.xz
tar xvJf qemu-8.1.1.tar.xz
rm -rf qemu-8.1.1.tar.xz
cd qemu-8.1.1
mkdir build
cd build
../configure --target-list=riscv64-softmmu
make -j$(nproc)
```

**Note**: The meaning of `configure`'s configuration parameters is explained as follows **(this is just a staged content and should be updated periodically)**:

- `--target-list=riscv64-softmmu`: Check system emulator.
