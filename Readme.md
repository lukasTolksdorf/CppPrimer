# C++ Primer

This repository is a collection of usefull material to get started with C++ if you already have some basic knowledge.

## General Setup
### Development Environment

You will ne some sort of editor and compiler to get started. It might be easier if you use an 
Integrated Development Environment (IDE) which integrated the compiler (and Debugger) nicely into a text editor.
A good cross platform solution would be [Visual Code] (https://code.visualstudio.com/docs/languages/cpp) with the C++
extension. Follow the instructions and install the compiler of your choice. 

### Build System

You to tell you compiler where to find your source files and what to do with them. Afterwards you probably want to tell
the linker how to connect your compiler output (object files) to get your executable https://git-scm.com/ (or library). Your IDE usually includes
some form of "c++ project" settings, which does the job, but then you are bound to your IDE. You should rather use a general
build system like cmake or bazel to keep your freedom. For now, we go with [CMake](https://cmake.org/). Visual Code can 
integrate CMake through its C++ extension.

### Version Control System

Just use [git](https://git-scm.com/)

## First Project

I provided you a first project [here](https://github.com/lukasTolksdorf/cmake_templates). Go clone in with

```bash
cd <local path where you want to clone it into>
git clone --recursive https://github.com/lukasTolksdorf/cmake_templates
```

The general Structur is a follows:

```
.
├── CMakeLists.txt
├── common
│   └── ...
├── extern
│   └── googletest
│       └── ...
├── firstLib
│   ├── CMakeLists.txt
│   ├── include
│   │   └── firstLib
│   │       └── PublicClass.hpp
│   ├── src
│   │   ├── InternalClass.cc
│   │   ├── InternalClass.hpp
│   │   └── PublicClass.cc
│   └── test
│       ├── CMakeLists.txt
│       └── PublicClass_test.cc
└── FirstProgramm
    ├── CMakeLists.txt
    └── HelloWorld.cc
```

### CMakeLists.txt

Entrypoint for cmake. It tells cmake what directories to include with other CMakeLists.txt files, containing the targets.
It also does the general setup and includes further cmake modules from the common subdirectory.

### extern

place to put all your external dependencies as git submodules. Already includes googletest libraries

### FirstProgramm

contains a source files and a CMakeLists.txt . The later defines that the HelloWorld.cc file shall be translated into an
executable and that it depends on the static library firstLib.

### firstLib

contains a static library as well as tests (rather test dummies). Have a look at the CMakeLists.txt and play with the content.
the test target depends on googletest. By linkihttps://www.youtube.com/watch?v=iz5Qx18H6lgng gtest_main to it, an executable created which includes the tests. Try
running it.

## General Information

 * CppCon:
   * [The best parts of C++](https://www.youtube.com/watch?v=iz5Qx18H6lg)
   * [Smart Pointers](https://www.youtube.com/watch?v=xGDLkt-jBJ4&list=PLHTh1InhhwT6KhvViwRiTR7I5s09dLCSw&index=78&t=0s)
   * [RAII and the Rule of Zero](https://www.youtube.com/watch?v=7Qgd9B1KuMQ&list=PLHTh1InhhwT6KhvViwRiTR7I5s09dLCSw&index=134&t=0s)
   * [Object-Oriented Programming](https://www.youtube.com/watch?v=32tDTD9UJCE&list=PLHTh1InhhwT6KhvViwRiTR7I5s09dLCSw&index=147&t=0s)
   * [Function and Class Templates](https://www.youtube.com/watch?v=LMP_sxOaz6g&list=PLHTh1InhhwT6KhvViwRiTR7I5s09dLCSw&index=158&t=0s)
 * C++ Weekly:
   * [Important part of C++98](https://www.youtube.com/watch?v=78Y_LRZPVRg)
   * [Important part of C++11](https://www.youtube.com/watch?v=D5n6xMUKU3A)
   * [Important part of C++14](https://www.youtube.com/watch?v=mXxNvaEdNHI)
   * [Important part of C++17](https://www.youtube.com/watch?v=QpFjOlzg1r4)
 * to be continued


