## path
```
$ADT/sdk/
    /ndk/
```
* make toolchain
```
sh $ADT/ndk/build/tools/make-standalone-toolchain.sh --platform=android-8 --toolchain=arm-linux-androideabi-4.9 --install-dir=$ADT/arm-android-8/toolchain

```
* set env
```
setenv NDK_HOME $ADT/ndk
setenv NDK_HOST arm-linux-androideabi
setenv NDK_TOOLCHAIN $ADT/arm-android-8/toolchain
set path=($path $ADT/sdk/tools $ADT/sdk/platform-tools $NDK_HOME $NDK_TOOLCHAIN/bin)
```

## GMP
install libraries to $HOME/adt/libs
```
./configure --host=arm-linux-androideabi --prefix=$HOME/adt/libs --enable-cxx
```

```
  Version:           GNU MP 6.0.0
  Host type:         arm-unknown-linux-androideabi
  ABI:               standard
  Install prefix:    /home/shigeo/adt/libs
  Compiler:          arm-linux-androideabi-gcc -std=gnu99
  Static libraries:  yes
  Shared libraries:  yes
```

```
make -j
make install
```

## Remark
You must unset NDK_TOOLCHAIN and repalce $NDK_TOOLCHAIN/bin with $NDK_HOME/toolchains/arm-linux-androideabi-4.9/prebuilt/linux-x86_64/bin to path.
