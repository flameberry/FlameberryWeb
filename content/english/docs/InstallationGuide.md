---
title: "Installation Guide"
# meta title
meta_title: "Installation Guide"
# meta description
description: "Documentation for you to get started with the Flameberry Engine, download it, install and run it."
# save as draft
draft: false
---

{{< toc >}}

## Getting Started with Flameberry Engine

Welcome to Flameberry Engine, a powerful and versatile game engine designed to empower developers in creating immersive and dynamic gaming experiences. This guide will walk you through the process of cloning the project, setting up dependencies, and building Flameberry Engine for the first time. 

### Supported Platforms

- **MacOS** - Supported
- **Windows** - Yet to Test
- **Linux** - Yet to Test

### Prerequisites

Before you begin, ensure that your development environment meets the following prerequisites:

#### C++17
Flameberry Engine requires C++17 features. Ensure that you have a C++ compiler that supports this standard.

#### Python 3
Python 3.x.x must be installed in your system to be able to run the Setup Scripts. Python is used to download various tools required for building Flameberry, like CMake and Vulkan SDK. Also the Nvidia PhysX and Assimp Libraries are built for your system using the Setup Script. Meta data of the local installation is stored via Python. So Python is mandatory, for setting up the project.

#### CMake (optional, but recommended)
Flameberry Engine uses CMake as it's primary build system. It is preferred that you have CMake installed with a version of >= 3.20.0, although the build process is only tested for the version 3.27.7.

{{< notice "tip" >}}
**You can skip installing CMake, as the Setup script already takes care of the installation, if not installed already.**
{{< /notice >}}

#### Vulkan SDK (optional, but recommended)
Flameberry Engine uses Vulkan as the Graphics API, so the Vulkan SDK is required. It is preferred that a Vulkan SDK is installed of version >= 1.3.x.x, note that Flameberry is tested with the version 1.3.268.1.

{{< notice "tip" >}}
**You can skip installing Vulkan SDK, as the Setup script already takes care of the installation, if not installed already.**
{{< /notice >}}

#### Visual Studio (For Windows Only)
Flameberry Engine uses Nvidia PhysX as the Physics Engine and to build the library on Windows, only Visual Studio presets are available. Hence, unless you have the Nvidia PhysX libraries already installed, you need to have Visual Studio 15/16/17 installed.

{{< notice "note" >}}
**If you have the libraries already installed (Both 'checked' and 'release' configurations are required) then make sure to copy paste those libraries in the following folders:**
```bash
Flameberry/vendor/PhysX/physx/bin/windows/checked
Flameberry/vendor/PhysX/physx/bin/windows/release 
```
{{< /notice >}}


### Build Steps
#### Clone the Repository

Start by cloning the Flameberry Engine repository to your local machine. Open a terminal and execute the following command:

```bash
git clone --recursive https://github.com/flameberry/FlameberryEngine
```

{{< notice "tip" >}}
**Make sure to use the `--recursive` flag to ensure you download all the submodules as well.**
{{< /notice >}}

#### Setup Dependencies

Navigate to the root directory of the cloned repository and run the setup script to check for dependencies like CMake, Vulkan SDK, Nvidia PhysX libraries and Assimp libraries and install them if not present:

```bash
cd FlameberryEngine
python Scripts/Setup.py
```

#### Build Flameberry Engine

Once the dependencies are set up, it's time to build Flameberry Engine. 

##### Do you have an IDE like Xcode or Visual Studio?
If you have any sort of IDE like Xcode (For Mac) or Visual Studio (For Windows), which is registered in CMake as a Generator Type, then the script has generated the project files in the `build/<GeneratorName>/` (`build/Xcode/`, `build/VisualStudio/` or `build/Auto/` in case of some other generator) folder. Now you can go to the folder and open the project file using the IDE and then run the project in any build configuration (`Release` config is preferred).

##### Do you have a standalone compiler like MinGW/GCC/Clang?
If you have any sort of standalone c++ compiler like MinGW/GCC/Clang then the script has already built the executable. You can find and run the executable in the following path:<br>

```bash
bin/<Configuration>/FlameberryEditor-<System>-<Architecture>/FlameberryEditor_<Configuration>
```
Where `Configuration` can be one of Debug/Release, `System` can be one of Windows/Darwin/Linux, `Architecture` can be one of x86_64/arm64/i386 etc.

#### Congratulations!
You have successfully cloned, set up dependencies, and built Flameberry Engine. You are now ready to explore the vast capabilities of our game engine and start developing your next gaming masterpiece.
