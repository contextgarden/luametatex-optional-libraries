# Make ConTeXt optional libraries

For native platform:

```
cmake -S . -B build -DCMAKE_BUILD_TYPE=Release
cmake --build build -j10
ls build/*.so # or other
```

Cross-compiling from Linux to Windows with mingw:

```
cmake -S . -B build-w64 --toolchain cross-windows.cmake -DCMAKE_BUILD_TYPE=Release
cmake --build build-w64 -j10
ls build-w64/*.dll
```
