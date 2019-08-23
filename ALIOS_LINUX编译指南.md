> [rv32m1_vega.patch.zip](https://github.com/alibaba/AliOS-Things/files/3442479/rv32m1_vega.patch.zip)
> 
> 打上这个patch试一试（解压要AliOS Things目录下，运行如下指令）：
> 
> ```shell
> git apply ./rv32m1_vega.patch
> ```
> 
> 在linux上是没有问题的。
> 
> 注意事项：
> 
> 1. toolchain的存放位置如下（**注意路径名称**）：
> 
> ```shell
> $ tree -L 3 ./build/compiler/
> ./build/compiler/
> └── riscv32-unknown-elf-gcc
>     └── Linux64
>         ├── bin
>         ├── include
>         ├── lib
>         ├── libexec
>         ├── riscv32-unknown-elf
>         └── share
> ```
> 
> 1. 这个toolchain需要安装依赖（参考[织女星开发板嵌入式开发环境搭建.pdf](https://github.com/open-isa-cn/vega-lite/blob/master/%E7%BB%87%E5%A5%B3%E6%98%9F%E5%BC%80%E5%8F%91%E6%9D%BF%E5%B5%8C%E5%85%A5%E5%BC%8F%E5%BC%80%E5%8F%91%E7%8E%AF%E5%A2%83%E6%90%AD%E5%BB%BA.pdf)）：
> 
> ```shell
> $ sudo apt install autoconf automake autotools-dev curl libmpc-dev libmpfr-dev libgmp-dev gawk build-essential bison flex texinfo gperf libtool patchutils bc zlib1g-dev libusb-1.0-0-dev libudev1 libudev-dev g++
> ```
> 
> 1. 同时需要创建软符号才能正常编译：
> 
> ```shell
> $ sudo ln -s /usr/lib/x86_64-linux-gnu/libmpfr.so.4.1.4 /usr/lib/x86_64-linux-gnu/libmpfr.so.6
> ```
> 
> 最终编译效果：
> 
> ```
> Making out/helloworld@rv32m1_vega/libraries/helloworld.a
> Making out/helloworld@rv32m1_vega/libraries/board_rv32m1_vega.a
> Making out/helloworld@rv32m1_vega/libraries/osal_aos.a
> Making out/helloworld@rv32m1_vega/libraries/rhino.a
> Making out/helloworld@rv32m1_vega/libraries/debug.a
> Making out/helloworld@rv32m1_vega/libraries/kernel_init.a
> Making out/helloworld@rv32m1_vega/libraries/arch_riscy.a
> Making out/helloworld@rv32m1_vega/libraries/kv.a
> Making out/helloworld@rv32m1_vega/libraries/mcu_rv32m1.a
> Making out/helloworld@rv32m1_vega/libraries/netmgr.a
> Making out/helloworld@rv32m1_vega/libraries/newlib_stub.a
> Making out/helloworld@rv32m1_vega/libraries/ulog.a
> Making out/helloworld@rv32m1_vega/libraries/vfs.a
> Making out/helloworld@rv32m1_vega/libraries/yloop.a
> Making helloworld@rv32m1_vega.elf
> 
> Making helloworld@rv32m1_vega.bin
> Making helloworld@rv32m1_vega.hex
> Can't parse memory configure, memory info get fail!
> 1048464
> 604f0e9b9f017e7b3077eea3cd4c2a5f
> Build complete: helloworld@rv32m1_vega
> ```
> 
> > `riscv32_vega` 这个board在最新的版本中默认不支持了。所以存在这些问题。



> [rv32m1_vega.patch.zip](https://github.com/alibaba/AliOS-Things/files/3442479/rv32m1_vega.patch.zip)
> 
> 打上这个patch试一试（解压要AliOS Things目录下，运行如下指令）：
> 
> ```shell
> git apply ./rv32m1_vega.patch
> ```
> 
> 在linux上是没有问题的。
> 
> 注意事项：
> 
> 1. toolchain的存放位置如下（**注意路径名称**）：
> 
> ```shell
> $ tree -L 3 ./build/compiler/
> ./build/compiler/
> └── riscv32-unknown-elf-gcc
>     └── Linux64
>         ├── bin
>         ├── include
>         ├── lib
>         ├── libexec
>         ├── riscv32-unknown-elf
>         └── share
> ```
> 
> 1. 这个toolchain需要安装依赖（参考[织女星开发板嵌入式开发环境搭建.pdf](https://github.com/open-isa-cn/vega-lite/blob/master/%E7%BB%87%E5%A5%B3%E6%98%9F%E5%BC%80%E5%8F%91%E6%9D%BF%E5%B5%8C%E5%85%A5%E5%BC%8F%E5%BC%80%E5%8F%91%E7%8E%AF%E5%A2%83%E6%90%AD%E5%BB%BA.pdf)）：
> 
> ```shell
> $ sudo apt install autoconf automake autotools-dev curl libmpc-dev libmpfr-dev libgmp-dev gawk build-essential bison flex texinfo gperf libtool patchutils bc zlib1g-dev libusb-1.0-0-dev libudev1 libudev-dev g++
> ```
> 
> 1. 同时需要创建软符号才能正常编译：
> 
> ```shell
> $ sudo ln -s /usr/lib/x86_64-linux-gnu/libmpfr.so.4.1.4 /usr/lib/x86_64-linux-gnu/libmpfr.so.6
> ```
> 
> 最终编译效果：
> 
> ```
> Making out/helloworld@rv32m1_vega/libraries/helloworld.a
> Making out/helloworld@rv32m1_vega/libraries/board_rv32m1_vega.a
> Making out/helloworld@rv32m1_vega/libraries/osal_aos.a
> Making out/helloworld@rv32m1_vega/libraries/rhino.a
> Making out/helloworld@rv32m1_vega/libraries/debug.a
> Making out/helloworld@rv32m1_vega/libraries/kernel_init.a
> Making out/helloworld@rv32m1_vega/libraries/arch_riscy.a
> Making out/helloworld@rv32m1_vega/libraries/kv.a
> Making out/helloworld@rv32m1_vega/libraries/mcu_rv32m1.a
> Making out/helloworld@rv32m1_vega/libraries/netmgr.a
> Making out/helloworld@rv32m1_vega/libraries/newlib_stub.a
> Making out/helloworld@rv32m1_vega/libraries/ulog.a
> Making out/helloworld@rv32m1_vega/libraries/vfs.a
> Making out/helloworld@rv32m1_vega/libraries/yloop.a
> Making helloworld@rv32m1_vega.elf
> 
> Making helloworld@rv32m1_vega.bin
> Making helloworld@rv32m1_vega.hex
> Can't parse memory configure, memory info get fail!
> 1048464
> 604f0e9b9f017e7b3077eea3cd4c2a5f
> Build complete: helloworld@rv32m1_vega
> ```
> 
> > `riscv32_vega` 这个board在最新的版本中默认不支持了。所以存在这些问题。
