## General Information

- CMake has its own language / syntax.
- At the beginning of each project must be a `CMakeList.txt` file. 
	- `CMakeList.txt` is a file that CMake recognizes as a build script file.
	- A project can have multiple `CMakeList.txt`, but only **one** in each directory.  For the one in the top level directory of the project, the following must be present at the top of the file:

```txt
cmake_minimum_required(VERSION 3.6) 
project(name_of_project)
```

- Minimum version is 3.0

### Use CMake to Build a Library

- The source files that compose the library must be in the `CMakeList.txt` file. 
- To do this we need to make a list of files and call the `add_library` function.

## Why is it useful?

- CMake provides an interface to specify build options and processes, without being concerned with compiler or operating system specific details. 
	- Note:  It only covers cross platform functionality for **building** the project, you are still responsible for the actual source code **running** on different platforms. 

