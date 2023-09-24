# Template For Practicing C++ Projects

![C++](https://img.shields.io/badge/C%2B%2B-11%2F14%2F17%2F20%2F23-blue)
![License](https://camo.githubusercontent.com/890acbdcb87868b382af9a4b1fac507b9659d9bf/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f6c6963656e73652d4d49542d626c75652e737667)

This template is adapted from [CppProjectTemplate](https://github.com/franneck94/CppProjectTemplate).

This is a template for Practicing C++ projects. What you get:

- Library, executable and test code separated in distinct folders
- Use of modern CMake for building and compiling
- External libraries installed and managed by
  - [CPM](https://github.com/cpm-cmake/CPM.cmake) Package Manager
- Code documentation with [Doxygen](https://doxygen.nl/)
- Tooling: Clang-Format, Cmake-Format, Clang-tidy

## Structure

``` text
├── CMakeLists.txt
├── app
│   ├── CMakesLists.txt
│   └── main.cpp
├── cmake
│   └── cmake modules
├── docs
│   ├── Doxyfile
│   └── html/
├── external
│   ├── CMakesLists.txt
│   ├── ...
└── src
    ├── CMakesLists.txt
    ├── my_lib.hpp
    └── my_lib.cpp

```

Library code goes into [src/](src/), main program code in [app/](app)

## Software Requirements

- CMake 3.27+
- GNU Makefile
- Doxygen
- MSVC 2017 (or higher), G++9 (or higher), Clang++9 (or higher)
- Optional: Makefile

## Building

First, clone this repo and do the preliminary work:

```shell
git clone --recursive https://github.com/snpara/cpp-practice-template
make prepare
```

- App Executable

```shell
cd build
cmake -DCMAKE_BUILD_TYPE=Release ..
cmake --build . --config Release --target main
cd app
./main
```

- Unit testing

```shell
cd build
cmake -DCMAKE_BUILD_TYPE=Debug ..
cmake --build . --config Debug --target unit_tests
cd tests
./unit_tests
```

- Documentation

```shell
cd build
cmake -DCMAKE_BUILD_TYPE=Debug ..
cmake --build . --config Debug --target docs
```

- Code Coverage (Unix only)

```shell
cd build
cmake -DCMAKE_BUILD_TYPE=Debug -DENABLE_COVERAGE=ON ..
cmake --build . --config Debug --target coverage
```

For more info about CMake see [here](./README_cmake.md).
