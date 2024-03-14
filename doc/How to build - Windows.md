# Building KatanaSlicer on Windows


## 0. Prerequisities

The following tools need to be installed on your computer:
- Microsoft Visual Studio version 16 2019 or 17 2022
- CMake
- git




## 1. Download sources

Clone the respository. Use a directory relatively close to the drive root, so the path is not too long. Avoid spaces and non-ASCII characters. To place it in `C:\src\KatanaSlicer`, run:
```
c:> mkdir src
c:> cd src
c:\src> git clone https://github.com/3DXTech/Katana.git
```


## 2.A Manual Build Instructions

_As an alternative, you can go to 2.B to compile PrusaSlicer using one automatic script._

### Compile the dependencies.
Dependencies are updated seldomly, thus they are compiled out of the KatanaSlicer source tree.
Open the MSVC x64 Native Tools Command Prompt and run the following:
```
cd c:\src\KatanaSlicer\deps
mkdir build
cd build
cmake ..
cmake --build .
```
Expect this to take some time. Note that both _Debug_ and _Release_ variants are built. You can force only the _Release_ build by passing `-DDEP_DEBUG=OFF` to the first CMake call.

### Generate Visual Studio project file for KatanaSlicer, referencing the precompiled dependencies.
Open the MSVC x64 Native Tools Command Prompt and run the following:
```
cd c:\src\KatanaSlicer\
mkdir build
cd build
cmake .. -DCMAKE_PREFIX_PATH="c:\src\KatanaSlicer\deps\build\destdir\usr\local"
```

Note that `CMAKE_PREFIX_PATH` must be absolute path. A relative path will not work.

### Compile KatanaSlicer. 

Double-click c:\src\KatanaSlicer\build\KatanaSlicer.sln to open in Visual Studio and select `PrusaSlicer_app_gui` as your startup project (right-click->Set as Startup Project).

Run Build->Rebuild Solution once to populate all required dependency modules. This is NOT done automatically when you Build/Run. If you run both Debug and Release variants, you will need to do this once for each.

Debug->Start Debugging or press F5

KatanaSlicer should start. You're up and running!
