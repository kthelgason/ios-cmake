ios-cmake
=========

A toolchain file and examples using cmake for iOS development.
This is a fork of https://github.com/cristeab/ios-cmake/

This version has been tested with XCode versions from 8.0 up to
and including 8.2.1 and iOS SDK 10.2.1. It is known not to work
for versions older than XCode 4.3.

In order to compile the static library for the iOS simulator 32 bit,
`cd` to the folder where the library sources reside, then:

```sh
mkdir build && cd build
cmake .. -DCMAKE_TOOLCHAIN_FILE=<path to iOS.toolchain.cmake> -DIOS_PLATFORM=SIMULATOR
make
make install
```

Once the library is compiled and installed, `cd` to the folder where the
application sources reside, then open XCode with:

```sh
open hello-app.xcodeproj
```

Set `IOS_PLATFORM` to `SIMULATOR64` to build for 64-bit iPhone simulator.
Set `IOS_PLATFORM` to `IOS` to build for device.
