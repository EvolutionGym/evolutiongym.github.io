---
layout: default
title: evogym.EvoSim
nav_order: 2
parent: evogym
grand_parent: Documentation
---

<!-- markdownlint-disable -->

<!-- <a href="..\evogym\sim.py#L0"><img align="right" style="float:right;" src="https://img.shields.io/badge/-source-cccccc?style=flat-square"></a>

# <kbd>module</kbd> `sim`
This module defines the EvoSim class which provides a clean interface to Evolution Gym's simulator. 

**Global Variables**
---------------
- **VOXEL_TYPES**
- **BASELINE_ENV_NAMES**


--- -->

<a href="..\evogym\sim.py#L15"><img align="right" style="float:right;" src="https://img.shields.io/badge/-source-cccccc?style=flat-square"></a>

## <kbd>class</kbd> `EvoSim`
Create, step, reset, and get data from an Evolution Gym simulation. 



**Args:**
 
 - <b>`world`</b> (EvoWorld):  object containing world voxel specification. 

<a href="..\evogym\sim.py#L26"><img align="right" style="float:right;" src="https://img.shields.io/badge/-source-cccccc?style=flat-square"></a>

### <kbd>method</kbd> `__init__`

```
__init__(world: EvoWorld) → None
```








---

<a href="..\evogym\sim.py#L97"><img align="right" style="float:right;" src="https://img.shields.io/badge/-source-cccccc?style=flat-square"></a>

### <kbd>method</kbd> `get_actuator_indices`

```
get_actuator_indices(robot_name: str) → ndarray
```

Returns the voxel indices a target robot's actuators in the simulation. 



**Args:**
 
 - <b>`robot_name`</b> (str):  name of robot. 



**Returns:**
 
 - <b>`np.ndarray`</b>:  `(n,)` array of actuator indices, where `n` is the number of actuators. 

---

<a href="..\evogym\sim.py#L110"><img align="right" style="float:right;" src="https://img.shields.io/badge/-source-cccccc?style=flat-square"></a>

### <kbd>method</kbd> `get_dim_action_space`

```
get_dim_action_space(robot_name: str) → int
```

Returns the number of actuators for a target robot in the simulation. 



**Args:**
 
 - <b>`robot_name`</b> (str):  name of robot. 



**Returns:**
 
 - <b>`int`</b>:  number of actuators. 

---

<a href="..\evogym\sim.py#L110"><img align="right" style="float:right;" src="https://img.shields.io/badge/-source-cccccc?style=flat-square"></a>

### <kbd>method</kbd> `get_time`

```
get_time() → int
```

Returns the current time as defined in the simulator. Time starts at `0` and is incremented each time the simulator steps. Time resets to `0` when the simulator is reset.



**Returns:**
 
 - <b>`int`</b>:  the current time. 

---

<a href="..\evogym\sim.py#L230"><img align="right" style="float:right;" src="https://img.shields.io/badge/-source-cccccc?style=flat-square"></a>

### <kbd>method</kbd> `object_orientation_at_time`

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

<a href="..\evogym\sim.py#L200"><img align="right" style="float:right;" src="https://img.shields.io/badge/-source-cccccc?style=flat-square"></a>

### <kbd>method</kbd> `object_pos_at_time`

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

<a href="..\evogym\sim.py#L215"><img align="right" style="float:right;" src="https://img.shields.io/badge/-source-cccccc?style=flat-square"></a>

### <kbd>method</kbd> `object_vel_at_time`

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

<a href="..\evogym\sim.py#L174"><img align="right" style="float:right;" src="https://img.shields.io/badge/-source-cccccc?style=flat-square"></a>

### <kbd>method</kbd> `pos_at_time`

```
pos_at_time(time: int) → ndarray
```

Returns positions of all point-masses in the simulation at time `time`. Use `EvoSim.get_time()` to get current measurements. 



**Args:**
 
 - <b>`time`</b> (int):  time at which to return measurements. 



**Returns:**
 
 - <b>`np.ndarray`</b>:  `(2, n)` array of measurements, where `n` is the number of points in the simulation. 

---

<a href="..\evogym\sim.py#L245"><img align="right" style="float:right;" src="https://img.shields.io/badge/-source-cccccc?style=flat-square"></a>

### <kbd>method</kbd> `reset`

```
reset() → None
```

Reset the simulation to time `0`. 

---

<a href="..\evogym\sim.py#L123"><img align="right" style="float:right;" src="https://img.shields.io/badge/-source-cccccc?style=flat-square"></a>

### <kbd>method</kbd> `set_action`

```
set_action(robot_name: str, action: ndarray) → None
```

Set an action for a target robot. This function updates the robot's actuator targets, but will not step the simulation. 



**Args:**
 
 - <b>`robot_name`</b> (str):  name of robot 
 - <b>`action`</b> (np.ndarray):  `(n,)` array of actions, where `n` is the number of actuators of the target robot. 

---

<a href="..\evogym\sim.py#L123"><img align="right" style="float:right;" src="https://img.shields.io/badge/-source-cccccc?style=flat-square"></a>

### <kbd>method</kbd> `step`

```
step() → None
```

Step the simulation. 

---

<a href="..\evogym\sim.py#L187"><img align="right" style="float:right;" src="https://img.shields.io/badge/-source-cccccc?style=flat-square"></a>

### <kbd>method</kbd> `vel_at_time`

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
