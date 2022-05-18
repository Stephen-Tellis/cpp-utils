## cpp-utils
Crispy utils for use in C++ development environments handpicked from around the web.

## Building (in ROS environments)

### Building with cmake

Install a library with [CMake](www.cmake.org):

```bash
mkdir build
cd build
cmake .. -DUSE_CMAKE=true
sudo make install
```

Note that `USE_CMAKE` defaults to `true` if catkin is not installed.

Uninstall the library with:

```bash
cd build
sudo make uninstall
```

Including stuff in a cmake project.
Add the following to *CmakeLists.txt*:

```
find_package(projectx)
include_directories(${projectx_INCLUDE_DIRS})
```

### Building with catkin

Build with [catkin](wiki.ros.org/catkin):

```bash
cd ~/catkin_ws/src
git clone git@github.com:abc/projectx.git
catkin_make_isolated -C ~/catkin_ws
```

or with [catkin command line tools](http://catkin-tools.readthedocs.org):

```bash
cd ~/catkin_ws/src
git clone git@github.com:abc/projectx.git
catkin build -w ~/catkin_ws projectx
```

Include an installed project into a catkin project with:
Add to *CMakeLists.txt*:
```
find_package(catkin COMPONENTS projectx)
include_directories(${catkin_INCLUDE_DIRS})
```

And to your *package.xml*:

```xml
<package>
  <build_depend>projectx</build_depend>
</package>
```

## References:
[kindr](https://github.com/ethz-asl/kindr)  
[Cyrill Stachniss C++](https://www.youtube.com/watch?v=sZK6ouwREXA&list=PLgnQpQtFTOGRM59sr3nSL8BmeMZR9GCIA)  
[Jason Turner](https://www.youtube.com/watch?v=HPMvU64RUTY&list=PLs3KjaCtOwSbij6EOk7K-ZgKKcxH7yVHC)  
