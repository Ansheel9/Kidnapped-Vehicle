# Kidnapped Vehicle :car: 
[![Udacity - Self-Driving Car NanoDegree](https://s3.amazonaws.com/udacity-sdc/github/shield-carnd.svg)](http://www.udacity.com/drive)

---

Udacity Self-Driving Car Engineer Nanodegree

Project 6

---

## Introduction

![Result](./images/track_one.gif)

Your car has been kidnapped and transported to a new location! Luckily it has a map of this location, a (noisy) GPS estimate of its initial location, and lots of (noisy) sensor and control data.

In this project we will implement a 2 dimensional particle filter in C++. Our particle filter will be given a map and some initial localization information (analogous to what a GPS would provide). At each time step our filter will also get observation and control data.

* Inputs:
    * one map contains landmarks
    * one initial location (e.g GPS) in the very beginning with big uncertainty.
    * noisy landmark observations in each timestamp while vehicle is moving.
* Outputs: 
    * The **blue circle** (with an black arrow inside) is the real-time estimation of the vehicle's location 
      and heading orientation from the particle filter.
* Ground truth: 
    * The **blue car** is the ground truth of the vehicle, including position and heading orientation. 
    It is only visualized for comparison purpose.
---

## Dependencies & Environment

* cmake >= 3.5
 * All OSes: [click here for installation instructions](https://cmake.org/install/)
 * Linux and Mac OS, you can also skip to installation of uWebSockets as it installs it as a dependency.
* make >= 4.1(mac, linux), 3.81(Windows)
  * Linux: make is installed by default on most Linux distros
  * Mac: [install Xcode command line tools to get make](https://developer.apple.com/xcode/features/)
  * Windows: [Click here for installation instructions](http://gnuwin32.sourceforge.net/packages/make.htm)
  * Linux and Mac OS, you can also skip to installation of uWebSockets as it installs it as a dependency.
* gcc/g++ >= 5.4
  * Linux: gcc / g++ is installed by default on most Linux distros
  * Mac: same deal as make - [install Xcode command line tools]((https://developer.apple.com/xcode/features/)
  * Windows: recommend using [MinGW](http://www.mingw.org/)
  * Linux and Mac OS, you can also skip to installation of uWebSockets as it installs it as a dependency.
* [uWebSockets](https://github.com/uWebSockets/uWebSockets)
  * Run either `install-mac.sh` or `install-ubuntu.sh`. This will install cmake, make gcc/g++ too.
  * If you install from source, checkout to commit `e94b6e1`, i.e.
    ```
    git clone https://github.com/uWebSockets/uWebSockets 
    cd uWebSockets
    git checkout e94b6e1
    ```
    Some function signatures have changed in v0.14.x.
* Simulator. You can download these from the [Udacity simulator releases tab](https://github.com/udacity/self-driving-car-sim/releases).  

## Basic Build Instructions

1. Clone this repo.
2. Clean the project: `$./clean.sh`
3. Build the project: `$./build.sh` 
4. Run the project: `$./run.sh`

> **NOTE**
> If you get any `command not found` problems, you will have to install the associated dependencies (for example, [cmake](https://cmake.org/install/))

## Directory Structure

The directory structure of this repository is as follows:

```
root
|   build.sh
|   clean.sh
|   CMakeLists.txt
|   README.md
|   run.sh
|
|___data
|   |   control_data.txt
|   |   gt_data.txt
|   |   map_data.txt
|   |
|   |___observation
|       |   observations_000001.txt
|       |   ... 
|       |   observations_002444.txt
|   
|___src
    |   helper_functions.h
    |   main.cpp
    |   map.h
    |   particle_filter.cpp
    |   particle_filter.h
```
## Project Structure

Traditional vehicles use GPS localization embedded in the navigation system. As long as a human is driving the car this localization is good enough.

The GPS localizes the car with an accuracy of about 2 meters giving the driver a general idea of where he/she is. The driver then visually percieves the world to get a sense of what's around. He/she can see how far the car is from the curb or stop sign and that is how he/she's able to maneuver the car.

For a self driving car, a 2 meter localization accuracy is simply not enough. It could be in a whole different lane or on the sidewalk and it wouldn't know. For safety reasons and to even make self driving maneuvers possible, the localization precision needs to be within a few centimeters.

To be able to localize itself, a self driving car needs to sense the world around. Since the most accurate sensor for distance measurement is the high resolution LiDAR, this is the way to go.

The self driving car also needs a map, but this is no usual map like in traditional navigation systems. The map that proves to be most useful is one made of landmark positions. The self driving car will rely on knowing where a building, stop sign, or light pole is in a given intersection, and then when measuring its distance to those landmarks is able to localize itself.

Most landmark maps are built using LiDAR measurements, recording the landmark positions while the car is being driven around by a human driver. This means that the self driving car has seen the streets before driving on them.

![training_img](./images/track_one.gif)

## Result

![training_img](./images/track_one.gif)

Implementation was declared as pass since the error and the execution time of code was in permissible limits.