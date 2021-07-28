Edge Based Tracking library
===================================================

What is EBT?
--------------

EBT is a library of C++ classes that implement edge based object tracking in robotics and vision, using textureless object detection and tracking of the 3D pose.  

Detection and tracking schemes are coherently integrated in a particle filtering framework on the special Euclidean group, SE(3), in which the visual tracking problem is tackled by maintaining multiple hypotheses of the object pose. For textureless object detection, an efficient chamfer matching is employed so that a set of coarse pose hypotheses is estimated from the matching between 2D edge templates of an object and a query image. Particles are then initialized from the coarse pose hypotheses by randomly drawing based on costs of the matching. To ensure the initialized particles are at or close to the global optimum, an annealing process is performed after the initialization. While a standard edge-based tracking is employed after the annealed initialization, this library emploies a refinement process to establish improved correspondences between projected edge points from the object model and edge points from an input image.

Check the [wiki](https://github.com/CognitiveRobotics/object_tracking_2D_dev/wiki) for more info.  

Quickstart
----------
In the root library folder execute:


```
#!bash
$ mkdir build
$ cd build
$ cmake ..
$ make check (optional, runs unit tests)
$ make install
```

Prerequisites:

- [Boost](http://www.boost.org/users/download/) >= 1.43 (Ubuntu: `sudo apt-get install libboost-all-dev`)
- [OpenGL](http://www.opengl.org/) >= 1.10 (Ubuntu: `sudo apt-get install libglew-dev`)
- [GLEW](http://glew.sourceforge.net/) >= 1.10 (Ubuntu: `sudo apt-get install libglew-dev`)
- [GLUT](http://www.opengl.org/resources/libraries/glut/) >=2.8.1 (Ubuntu: `sudo apt-get install freeglut3-dev`)
- [OpenCV](http://opencv.org/downloads.html) = 2.4 to 2.4.9 ~~(Ubuntu: `sudo apt-get install libopencv-dev`)~~ build from source
 -  Note: OpenCV has changed with respect to nonfree components of the library. Patented features such as SURF have now been moved to https://github.com/Itseez/opencv_contrib, and are thus no longer shipped with the standard Debian package. In 2.4.9, you must enable the `BUILD_opencv_nonfree` flag when compiling. Also, portions of the old C API have also chenged in newer verssions of OpenCV as well (>2.4.9), and is thus not recomended.
- [LAPACK](http://www.netlib.org/lapack/) >= 3.5 (Ubuntu: `sudo apt-get install liblapack3`)
- [CMake](http://www.cmake.org/cmake/resources/software.html) >= 2.6 (Ubuntu: `sudo apt-get install cmake`)

Additional Information
----------------------
### Author
[***Changhyun Choi***](http://www.cc.gatech.edu/~cchoi/About_Me.html) ([heanylab](https://github.com/heanylab))  
### Contributors
[***Prateek Singhal***] (http://www.cc.gatech.edu/~psinghal)
[***Ruffin White***](http://about.me/ruffin) ([ruffsl](https://github.com/ruffsl))  
[***Heni Ben Amor***](http://henibenamor.weebly.com/)


[![Build Status](https://travis-ci.org/CognitiveRobotics/object_tracking_2D.svg?branch=master)](https://travis-ci.org/CognitiveRobotics/object_tracking_2D)
