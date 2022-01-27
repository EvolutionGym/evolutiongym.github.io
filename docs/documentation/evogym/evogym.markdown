---
layout: default
title: evogym
has_children: true
nav_order: 1
# permalink: /documentation/evogym
parent: Documentation
---

<!-- markdownlint-disable -->

<!-- <a href="https://github.com/EvolutionGym/evogym/blob/main/evogym/utils.py#L0"><img align="right" style="float:right;" src="https://img.shields.io/badge/-source-cccccc?style=flat-square"></a>

# <kbd>module</kbd> `utils`




**Global Variables**
---------------
- **VOXEL_TYPES**
- **BASELINE_ENV_NAMES**

--- -->



## <kbd>function</kbd> `get_uniform` <a href="https://github.com/EvolutionGym/evogym/blob/main/evogym/utils.py#L55"><img align="right" style="float:right;" src="https://img.shields.io/badge/-source-cccccc?style=flat-square"></a>
{: .mt-6}
```
get_uniform(x: int) → ndarray
```

Return a uniform distribution of a given size. 



**Args:**
 
 - <b>`x`</b> (int):  size of distribution. 



**Returns:**
 
 - <b>`np.ndarray`</b>:  array representing the probability distribution. 


---



## <kbd>function</kbd> `draw` <a href="https://github.com/EvolutionGym/evogym/blob/main/evogym/utils.py#L67"><img align="right" style="float:right;" src="https://img.shields.io/badge/-source-cccccc?style=flat-square"></a>

```
draw(pd: ndarray) → int
```

Sample from a probability distribution. 



**Args:**
 
 - <b>`pd`</b> (np.ndarray):  array representing the probability of sampling each element. 



**Returns:**
 
 - <b>`int`</b>:  sampled index. 


---



## <kbd>function</kbd> `sample_robot` <a href="https://github.com/EvolutionGym/evogym/blob/main/evogym/utils.py#L89"><img align="right" style="float:right;" src="https://img.shields.io/badge/-source-cccccc?style=flat-square"></a>

```
sample_robot(
    robot_shape: Tuple[int, int],
    pd: ndarray = None
) → Tuple[ndarray, ndarray]
```

Return a randomly sampled robot of a particular size. 



**Args:**
 
 - <b>`robot_shape`</b> (Tuple(int, int)):  robot shape to sample `(h, w)`. 
 - <b>`pd`</b> (np.ndarray):  `(5,)` array representing the probability of sampling each robot voxel (empty, rigid, soft, h_act, v_act). Defaults to a custom distribution. (default = None) 



**Returns:**
 
 - <b>`Tuple[np.ndarray, np.ndarray]`</b>:  randomly sampled (valid) robot voxel array and its associated connections array. 


---



## <kbd>function</kbd> `is_connected` <a href="https://github.com/EvolutionGym/evogym/blob/main/evogym/utils.py#L170"><img align="right" style="float:right;" src="https://img.shields.io/badge/-source-cccccc?style=flat-square"></a>

```
is_connected(robot: ndarray) → bool
```

Returns whether or not a certain robot is connected by running floodfill. 



**Args:**
 
 - <b>`robot`</b> (np.ndarray):  array specifing the voxel structure of the robot. 



**Returns:**
 
 - <b>`bool`</b>:  whether or not the robot is connected. 


---



## <kbd>function</kbd> `has_actuator` <a href="https://github.com/EvolutionGym/evogym/blob/main/evogym/utils.py#L204"><img align="right" style="float:right;" src="https://img.shields.io/badge/-source-cccccc?style=flat-square"></a>

```
has_actuator(robot: ndarray) → bool
```

Returns whether or not a certain robot has an actuator. 

**Args:**
 
 - <b>`robot`</b> (np.ndarray):  array specifing the voxel structure of the robot. 



**Returns:**
 
 - <b>`bool`</b>:  whether or not the robot has an actuator. 


---


## <kbd>function</kbd> `get_full_connectivity` <a href="https://github.com/EvolutionGym/evogym/blob/main/evogym/utils.py#L220"><img align="right" style="float:right;" src="https://img.shields.io/badge/-source-cccccc?style=flat-square"></a>


```
get_full_connectivity(robot: ndarray) → ndarray
```

Returns a connections array given a connected robot structure. Assumes all adjacent voxels are connected. 



**Args:**
 
 - <b>`robot`</b> (np.ndarray):  array specifing the voxel structure of the robot. 



**Returns:**
 
 - <b>`np.ndarray`</b>:  `(2, k)` array specifying `k` pairwise voxel connections. Voxels are specified by their index into the 1D array `np.flatten(robot)`. 


---



## <kbd>function</kbd> `hashable` <a href="https://github.com/EvolutionGym/evogym/blob/main/evogym/utils.py#L259"><img align="right" style="float:right;" src="https://img.shields.io/badge/-source-cccccc?style=flat-square"></a>

```
hashable(robot: ndarray) → str
```

Returns a hashable representation of a robot. 



**Args:**
 
 - <b>`robot`</b> (np.ndarray):  array specifing the voxel structure of the robot. 



**Returns:**
 
 - <b>`str`</b>:  string representation of the robot. 


---



## <kbd>constant</kbd> `BASELINE_ENV_NAMES` <a href="https://github.com/EvolutionGym/evogym/blob/main/evogym/utils.py#L17"><img align="right" style="float:right;" src="https://img.shields.io/badge/-source-cccccc?style=flat-square"></a>

```
BASELINE_ENV_NAMES: list[str]
```

List of all `32` evogym environment names. 

---




## <kbd>constant</kbd> `VOXEL_TYPES` <a href="https://github.com/EvolutionGym/evogym/blob/main/evogym/utils.py#L8"><img align="right" style="float:right;" src="https://img.shields.io/badge/-source-cccccc?style=flat-square"></a>

```
VOXEL_TYPES: Dict[str, int] = {
    'EMPTY': 0,
    'RIGID': 1,
    'SOFT': 2,
    'H_ACT': 3,
    'V_ACT': 4,
    'FIXED': 5,
}
```

Dictionary mapping voxel names to values. 

---

_This file was automatically generated via [lazydocs](https://github.com/ml-tooling/lazydocs)._
