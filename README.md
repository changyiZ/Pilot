# Pilot Engine

<p align="center">
  <a href="https://games104.boomingtech.com">
    <img src="engine/source/editor/resource/PilotEngine.png" width="400" alt="Pilot Engine logo">
  </a>
</p>

**Pilot Engine** is a tiny game engine used for the [gams104](https://games104.boomingtech.com) course.

## Continuous build status    
    
Build Type | Status  
:-: | :-:  
**Build Linux** | [![Build Linux](https://github.com/BoomingTech/Pilot/actions/workflows/build_linux.yml/badge.svg)](https://github.com/BoomingTech/Pilot/actions/workflows/build_linux.yml)  
**Build MacOS** | [![Build MacOS](https://github.com/BoomingTech/Pilot/actions/workflows/build_macos.yml/badge.svg)](https://github.com/BoomingTech/Pilot/actions/workflows/build_macos.yml)  

## Prerequisites

To build Pilot, you must first install the following tools.

### Windows 10/11
- Visual Studio 2019 (or more recent)
- CMake 3.19 (or more recent)
- Git 2.1 (or more recent)

### MacOS >= 10.15 (x86_64)
- Xcode 12.3 (or more recent)
- CMake 3.19 (or more recent)
- Git 2.1 (or more recent)

### Ubuntu 20.04
 - apt install the following packages
```
apt install libxrandr-dev
apt install libxrender-dev
apt install libxinerama-dev
apt install libxcursor-dev
apt install libxi-dev
apt install libglvnd-dev
apt install libvulkan-dev
apt install clang
apt install libc++-dev
apt install vulkan-validationlayers
apt install mesa-vulkan-drivers
```  
- [CMake](https://github.com/Kitware/CMake/releases?page=3) (The version of the cmake provided by apt is too low)
- [NVIDIA driver](https://docs.nvidia.com/cuda/cuda-installation-guide-linux/index.html#runfile) (The AMD and Intel driver is open-source, and thus is installed automatically by mesa-vulkan-drivers)

## Build Pilot

### Build on Windows
You may execute the **build_windows.bat**. This batch file will generate the projects, and build the **Release** config of **Pilot Engine** automatically. After successful build, you can find the PilotEditor.exe at the **bin** directory.

Or you can use the following command to generate the **Visual Studio** project firstly, then open the solution in the build directory and build it manually.
```
cmake -S engine/ -B build
```

### Build on MacOS

> The following build instructions only tested on specific hardware of x86_64, and do not support M1 chips. For M1 compatible, we will release later.

To compile Pilot, you must have the most recent version of Xcode installed.
Then run 'cmake' from the project's root directory, to generate a project of Xcode.

```
cmake -S engine/ -B build -G "Xcode"
```
and you can build the project with 
```
cmake --build build --config Release
```

### Build on Ubuntu 20.04 
You can execute the **build_linux.sh** to build the binaries.  
