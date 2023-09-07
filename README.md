# Building a SwiftUI app with CMake Example

This is a simple example of using CMake to build a SwiftUI application.

Please note, this was tested using CMake 3.27.4. As Swift support in CMake is relatively new this may not work as instructed in other versions of CMake.

## Usage

### Building for macOS

```
cmake -GNinja -S . -B build
cmake --build build
open build/Foobar.app
```

### Building for iPhoneOS

WARNING: iPhoneOS build is still not working so this will crash when launched.

Make sure you launch an instance of the Simulator running the same version if iOS being targetted (in this example, that's 16.4).

```
cmake -S . -B build -GNinja \
    -DCMAKE_SYSTEM_NAME=iOS \
    -DCMAKE_OSX_DEPLOYMENT_TARGET=16.4 \
    -DCMAKE_Swift_COMPILER_TARGET=arm64-apple-ios16.4
cmake --build build
xcrun simctl install booted build/Foobar.app
xcrun simctl launch booted com.example.Foobar
```