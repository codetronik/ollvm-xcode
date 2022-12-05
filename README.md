# LLVM Obfuscator for Xcode

```sh
$ git clone -b swift-5.7.1-RELEASE --single-branch https://github.com/apple/llvm-project
$ cd llvm-project
```

copy & overwrite `/llvm` from this repository to `/llvm-project/llvm`

```sh
$ cmake -S llvm -B Release -DCMAKE_BUILD_TYPE=Release -DLLVM_ENABLE_NEW_PASS_MANAGER=OFF -DLLVM_CREATE_XCODE_TOOLCHAIN=ON -DLLVM_ENABLE_PROJECTS="clang;libcxx;libcxxabi" 
$ cd Release
$ cd bin
$ sudo cp clang-14 /Applications/Xcode.app/Contents/Developer/Toolchains/XcodeDefault.xctoolchain/usr/bin
$ cd /Applications/Xcode.app/Contents/Developer/Toolchains/XcodeDefault.xctoolchain/usr/bin
$ sudo cp clang clang_org
$ sudo cp clang-14 clang
```

## Compile option example
``-mllvm -sub -mllvm -sub_loop=1 -mllvm -fla -mllvm -split -mllvm -split_num=5 -mllvm -bcf -mllvm -bcf_loop=2 -mllvm -bcf_prob=100 -mllvm -sobf`` 
