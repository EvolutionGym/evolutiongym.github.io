---
layout: default
title: evogym.envs.EvoGymBase
nav_order: 5
parent: evogym (subclasses + helpers)
grand_parent: Documentation
---

# envs.EvoGymBase
{: .no_toc }
{: .mt-6}
Extend this class for creating `gym`-like environments (inherits from `gym.Env`).

Quicklinks: &nbsp; [EvoWorld](world.markdown), &nbsp; [EvoSim](sim.markdown), &nbsp; [EvoViewer](viewer.markdown), &nbsp; [WorldObject](worldobject.markdown), &nbsp; [envs.EvoGymBase](base.markdown), &nbsp; [helper functions and metadata](evogym.markdown)

---

## Page Outline
{: .no_toc .text-delta }

1. TOC
{:toc}

---


## <kbd>class</kbd> `EvoGymBase` <a href="https://github.com/EvolutionGym/evogym/blob/main/evogym/envs/base.py#L16"><img align="right" style="float:right;" src="https://img.shields.io/badge/-source-cccccc?style=flat-square"></a>
{: .mt-6}
Base class for all Evolution Gym environments. 



**Args:**
 
 - <b>`world`</b> (EvoWorld):  object specifying the voxel layout of the environment. 



### <kbd>function</kbd> `__init__` <a href="https://github.com/EvolutionGym/evogym/blob/main/evogym/envs/base.py#L23"><img align="right" style="float:right;" src="https://img.shields.io/badge/-source-cccccc?style=flat-square"></a>

```
__init__(world: EvoWorld) → None
```






---

#### <kbd>property</kbd> default_viewer

Returns the environment's default viewer. 



**Returns:**
 
 - <b>`EvoSim`</b>:  viewer object to return. 

---

#### <kbd>property</kbd> sim

Returns the environment's simulation. 



**Returns:**
 
 - <b>`EvoSim`</b>:  simulation object to return. 

---

#### <kbd>property</kbd> unwrapped

Completely unwrap this env. 



**Returns:**
 
 - <b>`gym.Env`</b>:  The base non-wrapped gym.Env instance 



---



### <kbd>function</kbd> `close` <a href="https://github.com/EvolutionGym/evogym/blob/main/evogym/envs/base.py#L97"><img align="right" style="float:right;" src="https://img.shields.io/badge/-source-cccccc?style=flat-square"></a>

```
close() → None
```

Close the simulation. 

---



### <kbd>function</kbd> `get_actuator_indices` <a href="https://github.com/EvolutionGym/evogym/blob/main/evogym/envs/base.py#L103"><img align="right" style="float:right;" src="https://img.shields.io/badge/-source-cccccc?style=flat-square"></a>

```
get_actuator_indices(robot_name: str) → ndarray
```

Returns the voxel indices a target robot's actuators in the environment's simulation. 



**Args:**
 
 - <b>`robot_name`</b> (str):  name of robot. 



**Returns:**
 
 - <b>`np.ndarray`</b>:  `(n,)` array of actuator indices, where `n` is the number of actuators. 

---



### <kbd>function</kbd> `get_ceil_obs` <a href="https://github.com/EvolutionGym/evogym/blob/main/evogym/envs/base.py#L306"><img align="right" style="float:right;" src="https://img.shields.io/badge/-source-cccccc?style=flat-square"></a>

```
get_ceil_obs(
    object_name: str,
    terrain_list: list,
    sight_dist: int,
    sight_range: float = 5
) → ndarray
```

Observation helper-function. Computes an observation describing the shape of the terrain above the target object. Specifically, for each voxel to the left and right of the target object's center of mass (along with the voxel containing the center of mass), the following observation is computed: min(y-distance in voxels to the nearest terrain object above the target object's center of mass, `sight_range`). Results are returned in a 1D numpy array. 



**Args:**
 
 - <b>`object_name`</b> (str):  name of target object. 
 - <b>`terrain_list`</b> (list[str]):  names of objects to be considered terrain in the computation. 
 - <b>`sight_dist`</b> (int):  number of voxels to the left and right of the target object's center of mass for which an observation should be returned. 
 - <b>`sight_range`</b> (float):  the max number of voxels above the object that can be seen. (default = 5) 



**Returns:**
 
 - <b>`np.ndarray`</b>:  `(2 * sight_range + 1, )` array of distance observations. 

---



### <kbd>function</kbd> `get_dim_action_space` <a href="https://github.com/EvolutionGym/evogym/blob/main/evogym/envs/base.py#L115"><img align="right" style="float:right;" src="https://img.shields.io/badge/-source-cccccc?style=flat-square"></a>

```
get_dim_action_space(robot_name: str) → int
```

Returns the number of actuators for a target robot in the environment's simulation. 



**Args:**
 
 - <b>`robot_name`</b> (str):  name of robot. 



**Returns:**
 
 - <b>`int`</b>:  number of actuators. 

---



### <kbd>function</kbd> `get_floor_obs` <a href="https://github.com/EvolutionGym/evogym/blob/main/evogym/envs/base.py#L253"><img align="right" style="float:right;" src="https://img.shields.io/badge/-source-cccccc?style=flat-square"></a>

```
get_floor_obs(
    object_name: str,
    terrain_list: list,
    sight_dist: int,
    sight_range: float = 5
) → ndarray
```

Observation helper-function. Computes an observation describing the shape of the terrain below the target object. Specifically, for each voxel to the left and right of the target object's center of mass (along with the voxel containing the center of mass), the following observation is computed: min(y-distance in voxels to the nearest terrain object below the target object's center of mass, `sight_range`). Results are returned in a 1D numpy array. 



**Args:**
 
 - <b>`object_name`</b> (str):  name of target object. 
 - <b>`terrain_list`</b> (list[str]):  names of objects to be considered terrain in the computation. 
 - <b>`sight_dist`</b> (int):  number of voxels to the left and right of the target object's center of mass for which an observation should be returned. 
 - <b>`sight_range`</b> (float):  the max number of voxels below the object that can be seen. (default = 5) 



**Returns:**
 
 - <b>`np.ndarray`</b>:  `(2 * sight_range + 1, )` array of distance observations. 

---



### <kbd>function</kbd> `get_ort_obs` <a href="https://github.com/EvolutionGym/evogym/blob/main/evogym/envs/base.py#L241"><img align="right" style="float:right;" src="https://img.shields.io/badge/-source-cccccc?style=flat-square"></a>

```
get_ort_obs(object_name: str)
```

Observation helper-function. Returns the orientation of a target object. 



**Args:**
 
 - <b>`object_name`</b> (str):  name of object 



**Returns:**
 
 - <b>`np.ndarray`</b>:  `(1,)` array of the object's orientation. 

---



### <kbd>function</kbd> `get_pos_com_obs` <a href="https://github.com/EvolutionGym/evogym/blob/main/evogym/envs/base.py#L199"><img align="right" style="float:right;" src="https://img.shields.io/badge/-source-cccccc?style=flat-square"></a>

```
get_pos_com_obs(object_name: str) → ndarray
```

Observation helper-function. Computes the position of the center of mass of a target object by averaging the positions of the object's point masses. 



**Args:**
 
 - <b>`object_name`</b> (str):  name of object 



**Returns:**
 
 - <b>`np.ndarray`</b>:  `(2,)` array of the position of the center of mass. 

---



### <kbd>function</kbd> `get_relative_pos_obs` <a href="https://github.com/EvolutionGym/evogym/blob/main/evogym/envs/base.py#L227"><img align="right" style="float:right;" src="https://img.shields.io/badge/-source-cccccc?style=flat-square"></a>

```
get_relative_pos_obs(object_name: str)
```

Observation helper-function. Computes the positions of a target object's point masses relative to their center of mass. 



**Args:**
 
 - <b>`object_name`</b> (str):  name of object 



**Returns:**
 
 - <b>`np.ndarray`</b>:  `(2n,)` array of positions, where `n` is the number of point masses. 

---

 

### <kbd>function</kbd> `get_time` <a href="https://github.com/EvolutionGym/evogym/blob/main/evogym/envs/base.py#L127"><img align="right" style="float:right;" src="https://img.shields.io/badge/-source-cccccc?style=flat-square"></a>

```
get_time() → int
```

Returns the current time as defined in the environment's simulator. Time starts at `0` and is incremented each time the environment steps. Time resets to `0` when the environment is reset. 



**Returns:**
 
 - <b>`int`</b>:  the current time. 

---



### <kbd>function</kbd> `get_vel_com_obs` <a href="https://github.com/EvolutionGym/evogym/blob/main/evogym/envs/base.py#L213"><img align="right" style="float:right;" src="https://img.shields.io/badge/-source-cccccc?style=flat-square"></a>

```
get_vel_com_obs(object_name: str) → ndarray
```

Observation helper-function. Computes the velocity of the center of mass of a target object by averaging the velocities of the object's point masses. 



**Args:**
 
 - <b>`object_name`</b> (str):  name of object 



**Returns:**
 
 - <b>`np.ndarray`</b>:  `(2,)` array of the velocity of the center of mass. 

---



### <kbd>function</kbd> `object_orientation_at_time` <a href="https://github.com/EvolutionGym/evogym/blob/main/evogym/envs/base.py#L186"><img align="right" style="float:right;" src="https://img.shields.io/badge/-source-cccccc?style=flat-square"></a>

```
object_orientation_at_time(time: int, object_name: str) → float
```

Returns an estimate of the orientation of an object at time `time`. Use `EvoGymBase.get_time()` to get current measurements. 



**Args:**
 
 - <b>`time`</b> (int):  time at which to return measurement. 
 - <b>`object_name`</b> (str):  name of object 



**Returns:**
 
 - <b>`float`</b>:  orientation with respect to x-axis in radians (increasing counter-clockwise) from the range [0, 2π]. 

---



### <kbd>function</kbd> `object_pos_at_time` <a href="https://github.com/EvolutionGym/evogym/blob/main/evogym/envs/base.py#L160"><img align="right" style="float:right;" src="https://img.shields.io/badge/-source-cccccc?style=flat-square"></a>

```
object_pos_at_time(time: int, object_name: str) → ndarray
```

Returns positions of all point-masses in a target object at time `time`. Use `EvoGymBase.get_time()` to get current measurements. 



**Args:**
 
 - <b>`time`</b> (int):  time at which to return measurements. 
 - <b>`object_name`</b> (str):  name of object 



**Returns:**
 
 - <b>`np.ndarray`</b>:  `(2, n)` array of measurements, where `n` is the number of point-masses in the target object. 

---



### <kbd>function</kbd> `object_vel_at_time` <a href="https://github.com/EvolutionGym/evogym/blob/main/evogym/envs/base.py#L173"><img align="right" style="float:right;" src="https://img.shields.io/badge/-source-cccccc?style=flat-square"></a>

```
object_vel_at_time(time: int, object_name: str) → ndarray
```

Returns velocities of all point-masses in a target object at time `time`. Use `EvoGymBase.get_time()` to get current measurements. 



**Args:**
 
 - <b>`time`</b> (int):  time at which to return measurements. 
 - <b>`object_name`</b> (str):  name of object 



**Returns:**
 
 - <b>`np.ndarray`</b>:  `(2, n)` array of measurements, where `n` is the number of point-masses in the target object. 

---



### <kbd>function</kbd> `pos_at_time` <a href="https://github.com/EvolutionGym/evogym/blob/main/evogym/envs/base.py#L136"><img align="right" style="float:right;" src="https://img.shields.io/badge/-source-cccccc?style=flat-square"></a>

```
pos_at_time(time: int) → ndarray
```

Returns positions of all point-masses in the environment's simulation at time `time`. Use `EvoGymBase.get_time()` to get current measurements. 



**Args:**
 
 - <b>`time`</b> (int):  time at which to return measurements. 



**Returns:**
 
 - <b>`np.ndarray`</b>:  `(2, n)` array of measurements, where `n` is the number of points in the environment's simulation. 

---



### <kbd>function</kbd> `render` <a href="https://github.com/EvolutionGym/evogym/blob/main/evogym/envs/base.py#L74"><img align="right" style="float:right;" src="https://img.shields.io/badge/-source-cccccc?style=flat-square"></a>

```
render(
    mode: str = 'screen',
    verbose: bool = False,
    hide_background: bool = False,
    hide_grid: bool = False,
    hide_edges: bool = False,
    hide_voxels: bool = False
) → Optional[ndarray]
```

Render the simulation. 



**Args:**
 
 - <b>`mode`</b> (str):  values of 'screen' and 'human' will render to a debug window. If set to 'img' will return an image array. 
 - <b>`verbose`</b> (bool):  whether or not to print the rendering speed (rps) every second. 
 - <b>`hide_background`</b> (bool):  whether or not to render the cream-colored background. If shut off background will be white. 
 - <b>`hide_grid`</b> (bool):  whether or not to render the grid. 
 - <b>`hide_edges`</b> (bool):  whether or not to render edges around all objects. 
 - <b>`hide_voxels`</b> (bool):  whether or not to render voxels. 



**Returns:**
 
 - <b>`Optional[np.ndarray]`</b>:  if `mode` is set to `img`, will return an image array. 

---



### <kbd>function</kbd> `reset` <a href="https://github.com/EvolutionGym/evogym/blob/main/evogym/envs/base.py#L48"><img align="right" style="float:right;" src="https://img.shields.io/badge/-source-cccccc?style=flat-square"></a>

```
reset() → None
```

Reset the simulation to the initial state. 

---



### <kbd>function</kbd> `step` <a href="https://github.com/EvolutionGym/evogym/blob/main/evogym/envs/base.py#L29"><img align="right" style="float:right;" src="https://img.shields.io/badge/-source-cccccc?style=flat-square"></a>

```
step(action: Dict[str, ndarray]) → bool
```

Step the environment by running physcis computations. 



**Args:**
 
 - <b>`action`</b> (Dict[str, np.ndarray]):  dictionary mapping robot names to actions. Actions are `(n,)` arrays, where `n` is the number of actuators in the target robot. 



**Returns:**
 
 - <b>`bool`</b>:  whether or not the simulation has reached an unstable state and cannot be recovered (`True` = unstable). 

---



### <kbd>function</kbd> `vel_at_time` <a href="https://github.com/EvolutionGym/evogym/blob/main/evogym/envs/base.py#L148"><img align="right" style="float:right;" src="https://img.shields.io/badge/-source-cccccc?style=flat-square"></a>

```
vel_at_time(time: int) → ndarray
```

Returns velocities of all point-masses in the environment's simulation at time `time`. Use `EvoGymBase.get_time()` to get current measurements. 



**Args:**
 
 - <b>`time`</b> (int):  time at which to return measurements. 



**Returns:**
 
 - <b>`np.ndarray`</b>:  `(2, n)` array of measurements, where `n` is the number of points in the environment's simulation. 




---

_This file was automatically generated via [lazydocs](https://github.com/ml-tooling/lazydocs)._
