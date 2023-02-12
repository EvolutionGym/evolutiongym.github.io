---
layout: default
title: evogym.EvoSim
nav_order: 2
parent: evogym (subclasses + helpers)
grand_parent: Documentation
---

# EvoSim
{: .no_toc }
{: .mt-6}
A steppable soft-body simulator which can be initialized from an `EvoWorld` instance.

Quicklinks: &nbsp; [EvoWorld](world.markdown), &nbsp; [EvoSim](sim.markdown), &nbsp; [EvoViewer](viewer.markdown), &nbsp; [WorldObject](worldobject.markdown), &nbsp; [envs.EvoGymBase](base.markdown), &nbsp; [helper functions and metadata](evogym.markdown)

---

## Page Outline
{: .no_toc .text-delta }

1. TOC
{:toc}

---

<!-- markdownlint-disable -->

<!-- <a href="https://github.com/EvolutionGym/evogym/blob/main/evogym/sim.py#L0"><img align="right" style="float:right;" src="https://img.shields.io/badge/-source-cccccc?style=flat-square"></a>

# <kbd>module</kbd> `sim`
This module defines the EvoSim class which provides a clean interface to Evolution Gym's simulator. 

**Global Variables**
---------------
- **VOXEL_TYPES**
- **BASELINE_ENV_NAMES**


--- -->

## <kbd>class</kbd> `EvoSim` <a href="https://github.com/EvolutionGym/evogym/blob/main/evogym/sim.py#L15"><img align="right" style="float:right;" src="https://img.shields.io/badge/-source-cccccc?style=flat-square"></a>
{: .mt-6}
Create, step, reset, and get data from an Evolution Gym simulation. 

**Args:**
 
 - <b>`world`</b> (EvoWorld):  object containing world voxel specification. 

### <kbd>method</kbd> `__init__` <a href="https://github.com/EvolutionGym/evogym/blob/main/evogym/sim.py#L26"><img align="right" style="float:right;" src="https://img.shields.io/badge/-source-cccccc?style=flat-square"></a>

```
__init__(world: EvoWorld) → None
```

---


### <kbd>method</kbd> `get_actuator_indices` <a href="https://github.com/EvolutionGym/evogym/blob/main/evogym/sim.py#L97"><img align="right" style="float:right;" src="https://img.shields.io/badge/-source-cccccc?style=flat-square"></a>

```
get_actuator_indices(robot_name: str) → ndarray
```

Returns the voxel indices a target robot's actuators in the simulation. 



**Args:**
 
 - <b>`robot_name`</b> (str):  name of robot. 



**Returns:**
 
 - <b>`np.ndarray`</b>:  `(n,)` array of actuator indices, where `n` is the number of actuators. 

---



### <kbd>method</kbd> `get_dim_action_space` <a href="https://github.com/EvolutionGym/evogym/blob/main/evogym/sim.py#L110"><img align="right" style="float:right;" src="https://img.shields.io/badge/-source-cccccc?style=flat-square"></a>

```
get_dim_action_space(robot_name: str) → int
```

Returns the number of actuators for a target robot in the simulation. 



**Args:**
 
 - <b>`robot_name`</b> (str):  name of robot. 



**Returns:**
 
 - <b>`int`</b>:  number of actuators. 

---



### <kbd>method</kbd> `get_time` <a href="https://github.com/EvolutionGym/evogym/blob/main/evogym/sim.py#L32"><img align="right" style="float:right;" src="https://img.shields.io/badge/-source-cccccc?style=flat-square"></a>

```
get_time() → int
```

Returns the current time as defined in the simulator. Time starts at `0` and is incremented each time the simulator steps. Time resets to `0` when the simulator is reset.



**Returns:**
 
 - <b>`int`</b>:  the current time. 

---



### <kbd>method</kbd> `object_orientation_at_time` <a href="https://github.com/EvolutionGym/evogym/blob/main/evogym/sim.py#L230"><img align="right" style="float:right;" src="https://img.shields.io/badge/-source-cccccc?style=flat-square"></a>

```
object_orientation_at_time(time: int, object_name: str) → float
```

Returns an estimate of the orientation of an object at time `time`. Use `EvoSim.get_time()` to get current measurements. 



**Args:**
 
 - <b>`time`</b> (int):  time at which to return measurement. 
 - <b>`object_name`</b> (str):  name of object 



**Returns:**
 
 - <b>`float`</b>:  orientation with respect to x-axis in radians (increasing counter-clockwise) from the range [0, 2π]. 

---



### <kbd>method</kbd> `object_pos_at_time` <a href="https://github.com/EvolutionGym/evogym/blob/main/evogym/sim.py#L200"><img align="right" style="float:right;" src="https://img.shields.io/badge/-source-cccccc?style=flat-square"></a>

```
object_pos_at_time(time: int, object_name: str) → ndarray
```

Returns positions of all point-masses in a target object at time `time`. Use `EvoSim.get_time()` to get current measurements. 



**Args:**
 
 - <b>`time`</b> (int):  time at which to return measurements. 
 - <b>`object_name`</b> (str):  name of object 



**Returns:**
 
 - <b>`np.ndarray`</b>:  `(2, n)` array of measurements, where `n` is the number of point-masses in the target object. 

---



### <kbd>method</kbd> `object_vel_at_time` <a href="https://github.com/EvolutionGym/evogym/blob/main/evogym/sim.py#L215"><img align="right" style="float:right;" src="https://img.shields.io/badge/-source-cccccc?style=flat-square"></a>

```
object_vel_at_time(time: int, object_name: str) → ndarray
```

Returns velocities of all point-masses in a target object at time `time`. Use `EvoSim.get_time()` to get current measurements. 



**Args:**
 
 - <b>`time`</b> (int):  time at which to return measurements. 
 - <b>`object_name`</b> (str):  name of object 



**Returns:**
 
 - <b>`np.ndarray`</b>:  `(2, n)` array of measurements, where `n` is the number of point-masses in the target object. 

---



### <kbd>method</kbd> `pos_at_time` <a href="https://github.com/EvolutionGym/evogym/blob/main/evogym/sim.py#L174"><img align="right" style="float:right;" src="https://img.shields.io/badge/-source-cccccc?style=flat-square"></a>

```
pos_at_time(time: int) → ndarray
```

Returns positions of all point-masses in the simulation at time `time`. Use `EvoSim.get_time()` to get current measurements. 



**Args:**
 
 - <b>`time`</b> (int):  time at which to return measurements. 



**Returns:**
 
 - <b>`np.ndarray`</b>:  `(2, n)` array of measurements, where `n` is the number of points in the simulation. 

---



### <kbd>method</kbd> `reset` <a href="https://github.com/EvolutionGym/evogym/blob/main/evogym/sim.py#L245"><img align="right" style="float:right;" src="https://img.shields.io/badge/-source-cccccc?style=flat-square"></a>

```
reset() → None
```

Reset the simulation to time `0`. 

---



### <kbd>method</kbd> `set_action` <a href="https://github.com/EvolutionGym/evogym/blob/main/evogym/sim.py#L123"><img align="right" style="float:right;" src="https://img.shields.io/badge/-source-cccccc?style=flat-square"></a>

```
set_action(robot_name: str, action: ndarray) → None
```

Set an action for a target robot. This function updates the robot's actuator targets, but will not step the simulation. 



**Args:**
 
 - <b>`robot_name`</b> (str):  name of robot 
 - <b>`action`</b> (np.ndarray):  `(n,)` array of actions, where `n` is the number of actuators of the target robot. 

---



### <kbd>method</kbd> `step` <a href="https://github.com/EvolutionGym/evogym/blob/main/evogym/sim.py#L32"><img align="right" style="float:right;" src="https://img.shields.io/badge/-source-cccccc?style=flat-square"></a>

```
step() → None
```

Step the simulation. 

---



### <kbd>method</kbd> `vel_at_time` <a href="https://github.com/EvolutionGym/evogym/blob/main/evogym/sim.py#L187"><img align="right" style="float:right;" src="https://img.shields.io/badge/-source-cccccc?style=flat-square"></a>

```
vel_at_time(time: int) → ndarray
```

Returns velocities of all point-masses in the simulation at time `time`. Use `EvoSim.get_time()` to get current measurements. 



**Args:**
 
 - <b>`time`</b> (int):  time at which to return measurements. 



**Returns:**
 
 - <b>`np.ndarray`</b>:  `(2, n)` array of measurements, where `n` is the number of points in the simulation. 




---

_This file was automatically generated via [lazydocs](https://github.com/ml-tooling/lazydocs)._
