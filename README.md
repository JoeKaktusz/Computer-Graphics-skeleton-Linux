# Skeleton for homeworks at the Computer Graphics course at BME for Linux users

The purpose of this repository is to help students to setup a development environment for those who don't want to use visual studio or not able to use for the Computer Graphics course at BME and for OpenGL 4.6. This tutorial was made for Linux users. Keep in mind that the commands were tested on an Ubuntu desktop so if you use an other distro the commands may be different.

## Disclaimers:
- This repository and the Computer Graphics course use OpenGL 4.6 since 2025/1 semester, so please check if your gpu is compatible with OpenGL 4.6 (It supposed to be compatible with OpenGL 3.3).
- You can check if your GPU support OpenGL 3.3 on these links: [Intel GPUs](https://www.intel.com/content/www/us/en/support/articles/000005524/graphics.html#primary-content), [Nvidia GPUs](https://en.wikipedia.org/wiki/List_of_Nvidia_graphics_processing_units), [AMD GPUs](https://en.wikipedia.org/wiki/List_of_AMD_graphics_processing_units).
- Make sure that you have the latest drivers for your GPU otherwise OpenGL 3.3 to 4.6 might not be supported. You can check which version of OpenGL supported on your machine with the following command:

```bash 
$ glxinfo | grep 'OpenGL version'
```
- It may require to install the **mesa-utils** package, which can be installed with the following command:

```bash 
$ sudo apt install mesa-utils
```

## Requirements:

- C/C++ compiler. Since OpenGL is a platform independent API, but since the course uses C++ we will use it aswell. (I recommend to use [gcc](https://gcc.gnu.org/) on Linux)
- CMake 3.10 or newer. We have to build our project from source and CMake deliver an easy solution for that problem. [What is CMake?](https://cmake.org/about/)
- OpenGL This will be our graphics API to gain acces to the power of the GPU. [What is OpenGL?](https://www.khronos.org/api/index_2016/opengl)
- Glad. This is a OpenGL Loader Generator to access OpenGL funcitons in a modern way. (It is included in the repository, but if you want to generate it for you you can try: [Generate GLAD](https://glad.dav0d.de/))
- GLM. OpenGL Mathematics is a math library for OpenGL included in the repo aswell. (You can read more about it of you want to [here](https://github.com/g-truc/glm))
- A code editor with CMake and C/C++ support. I recommend [CLion](https://www.jetbrains.com/clion/) or [VSCode](https://code.visualstudio.com/download) with C++ extensions (Optional, but highly recommended).

## Installation:

Install build-essential for C++ development

```bash 
$ sudo apt install build-essential
```

Install CMake

```bash 
$ sudo apt install cmake 
```

Install Mesa utilities for OpenGL development (includes OpenGL headers)

```bash 
$ sudo apt install mesa-common-dev libgl1-mesa-dev
```

Install Wayland development libraries

```bash 
$ sudo apt install libwayland-dev
```

Install Xorg development libraries (optional, for X11 support)

```bash 
$ sudo apt install libx11-dev libxrandr-dev libxinerama-dev libxcursor-dev
```

Install GLFW for managing OpenGL context

```bash 
$ sudo apt install libglfw3-dev
```

## How to build:

Okay so you have it all installed. now you have to build the source code. We are going to use CMake for that purpose. 

0. Make a build directory in your project directory (Where  the CMakeLists.txt is located) and switch there:

```bash 
$ mkdir build && cd build
```

1. Init CMake in the project:

```bash 
$ cmake ..
```

Make sure that CMakeLists.txt is in your project directory.
Now we have an initialized project by CMake. 

2. Build your project now with make:

```bash 
$ make
```

Done! Good job you built your first OpenGL application. 

3. Now the you have to run your binary file:

```bash 
$ ./openGLApp
```

The name of the program will be how you name your project in CMakeLists.txt.

## Important:

** You have to redo the building with initialize CMake process everytime you add some new files to the project**

---

## Congrats. You have it all. You can develop programs with OpenGL 4.6 on Ubuntu. 
