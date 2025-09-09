# opus

[Opus](https://opus-codec.org) binary builds for windows

> Opus is a totally open, royalty-free, highly versatile audio codec

[Opus](https://opus-codec.org) 预编译二进制包 (Windows)

> Opus 是一种完全开放、免版税且高度通用的音频编解码器

## Why

用到 opus 的地方还是挺多的: AI, 单片机, 多媒体, WEB 等等.

平时较为常见到 python 的 libopus 包, golang 的 opus-go 包, nodejs 的 node-opus 包等等,

但他们本质也只是 lib 封装, 底层还是调用的 opus 库的.

所以对于 windows 用户来说, 还是需要本机安装 opus 库的.

但是, 官方仓库默认 Release 发布的只有源码而已, 需要自己手工编译才能得到 dll 文件, 不是很友好.

所以, 这里提供了 opus 的预编译二进制包, 帮助 windows 用户安装 opus 库.

## Usage

下载需要版本的 zip 包后, 解压放置到自己喜欢的位置,

把目录路径加入到 环境变量 `Path` 中即可

## Build

如果你是喜欢自己DIY的人, 其实编译也很简单:

保证自己电脑已安装
- [Visual Studio 2022](https://visualstudio.microsoft.com/zh-hans/vs/)
- [Mingw64](https://github.com/niXman/mingw-builds-binaries/releases)
- [CMake](https://cmake.org/download/)

打开 mingw64 终端 (别用系统自带的 命令行 或 Powershell)

```shell
# 下载源码
git clone https://github.com/xiph/opus.git

# 构建编译目录
mkdir build

# 进入编译目录
cd build

# 预编译
cmake .. -DOPUS_BUILD_SHARED_LIBRARY=ON

# 编译
cmake --build . --config Release

# 在 build 目录下的 Release 目录下, 可以找到编译好的 opus.dll 文件
```

