---
layout: default
title: Getting Started
nav_order: 1
parent: Tutorials
---

<br/>

# Getting Started

Get started with the EvoGym codebase.
<br/><br/>

## Download

Clone the repo and submodules:

```shell
git clone --recurse-submodules https://github.com/deepers14159/RobotAPI.git
```
<br/>

## Requirements

* Python 3.7/3.8
* Linux, macOS, or Windows with [Visual Studios 2017](https://visualstudio.microsoft.com/vs/older-downloads/)
* [OpenGL](https://www.opengl.org//)
* [CMake](https://cmake.org/download/)
* [PyTorch](http://pytorch.org/)

<!--- (See [installation instructions](#opengl-installation-on-unix-based-systems) on Unix based systems) --->

On **Linux only**:

```shell
sudo apt-get install xorg-dev libglu1-mesa-dev
```

Either install Python dependencies with conda:

```shell
conda env create -f environment.yml
```

or with pip:

```shell
pip install -r requirements.txt
```

<br/>

## Build and Install Package

To build the C++ simulation, build all the submodules, and install `evogym` run the following command:

```shell
python setup.py install
``` 

<br/>

## Test Installation

cd to the `examples` folder and run the following script:

```shell
python gym_test.py
```

This script creates a random `5x5` robot in the `Walking-v0` environment. The robot is taking random actions. A window should open with a visualization of the environment -- kill the process from the terminal to close it.
