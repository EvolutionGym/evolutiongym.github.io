---
layout: default
title: evogym.EvoWorld
nav_order: 1
parent: evogym
grand_parent: Documentation
---

<!-- markdownlint-disable -->

<!-- <a href="https://github.com/EvolutionGym/evogym/blob/main/evogym/world.py#L0"><img align="right" style="float:right;" src="https://img.shields.io/badge/-source-cccccc?style=flat-square"></a>

# <kbd>module</kbd> `world`
This module defines the EvoWorld and WorldObject classes which provide a clean interface to store and manipulate objects in a Evolution Gym environment. 

**Global Variables**
---------------
- **VOXEL_TYPES**
- **BASELINE_ENV_NAMES**


--- -->



## <kbd>class</kbd> `EvoWorld` <a href="https://github.com/EvolutionGym/evogym/blob/main/evogym/world.py#L14"><img align="right" style="float:right;" src="https://img.shields.io/badge/-source-cccccc?style=flat-square"></a>
{: .mt-6}
Specify the layout of an Evolution Gym environment. 


### <kbd>method</kbd> `__init__` <a href="https://github.com/EvolutionGym/evogym/blob/main/evogym/world.py#L19"><img align="right" style="float:right;" src="https://img.shields.io/badge/-source-cccccc?style=flat-square"></a>

```
__init__() → None
```



---



### <kbd>method</kbd> `add_from_array` <a href="https://github.com/EvolutionGym/evogym/blob/main/evogym/world.py#L74"><img align="right" style="float:right;" src="https://img.shields.io/badge/-source-cccccc?style=flat-square"></a>

```
add_from_array(
    name: 'str',
    structure: 'ndarray',
    x: 'int',
    y: 'int',
    connections: 'Optional[ndarray]' = None
) → None
```

Add a single object to the world from array. 



**Args:**
 
 - <b>`name`</b> (str):  object name. 
 - <b>`structure`</b> (np.ndarray):  `(n, m)` array specifing the voxel structure of the object. See `evogym.VOXEL_TYPES`.  
 - <b>`x`</b> (int):  x-position of the bottom & leftmost voxel of the object. Starts at `0`. 
 - <b>`y`</b> (int):  y-position of the bottom & leftmost voxel of the object. Starts at `0`. 
 - <b>`connections`</b> (Optional[np.ndarray]):  `(2, k)` array specifying `k` pairwise voxel connections. Voxels are specified by their index into the 1D array `np.flatten(structure)`. The default behavior assumes all adjacent voxels are connected. (default = None) 

---



### <kbd>method</kbd> `add_from_json` <a href="https://github.com/EvolutionGym/evogym/blob/main/evogym/world.py#L39"><img align="right" style="float:right;" src="https://img.shields.io/badge/-source-cccccc?style=flat-square"></a>

```
add_from_json(file_path: 'str') → None
```

Add objects to an existing `EvoWorld` object from a `.json` environment specification file. These can be created using the EvoGym Design Tool. 



**Args:**
 
 - <b>`file_path`</b> (str):  path to file. Ex: `my_env.json`. 

---



### <kbd>method</kbd> `add_object` <a href="https://github.com/EvolutionGym/evogym/blob/main/evogym/world.py#L95"><img align="right" style="float:right;" src="https://img.shields.io/badge/-source-cccccc?style=flat-square"></a>

```
add_object(obj: 'WorldObject') → None
```

Add a single object to the world. 



**Args:**
 
 - <b>`obj`</b> (WorldObject):  object to add. 

---



### <kbd>classmethod</kbd> `from_json` <a href="https://github.com/EvolutionGym/evogym/blob/main/evogym/world.py#L24"><img align="right" style="float:right;" src="https://img.shields.io/badge/-source-cccccc?style=flat-square"></a>

```
from_json(file_path: 'str') → EvoWorld
```

Create an `EvoWorld` object from a `.json` environment specification file (these can be created using the EvoGym Design Tool) and return it. 



**Args:**
 
 - <b>`file_path`</b> (str):  path to file. Ex: `my_env.json`. 



**Returns:**
 
 - <b>`EvoWorld`</b>:  resulting `EvoWorld` object. 

---



### <kbd>method</kbd> `move_object` <a href="https://github.com/EvolutionGym/evogym/blob/main/evogym/world.py#L187"><img align="right" style="float:right;" src="https://img.shields.io/badge/-source-cccccc?style=flat-square"></a>

```
move_object(obj_name: 'str', x: 'int', y: 'int') → None
```

Move an object in world by name. 



**Args:**
 
 - <b>`obj_name`</b> (str):  object name. 
 - <b>`x`</b> (int):  x-position of the bottom & leftmost voxel of the object. Starts at `0`. 
 - <b>`y`</b> (int):  y-position of the bottom & leftmost voxel of the object. Starts at `0`. 

---



### <kbd>method</kbd> `pretty_print` <a href="https://github.com/EvolutionGym/evogym/blob/main/evogym/world.py#L209"><img align="right" style="float:right;" src="https://img.shields.io/badge/-source-cccccc?style=flat-square"></a>

```
pretty_print(voxels_per_line: 'int' = 50) → None
```

Print world to console for debugging. Voxels are specified by (R)igid, (S)oft, (H)orizontal Actuator, (V)ertical Actuator, (F)ixed. 



**Args:**
 
 - <b>`voxels_per_line`</b> (int):  Number of voxels to print per line -- reduce for smaller screens. (default = 50) 

---



### <kbd>method</kbd> `remove_object` <a href="https://github.com/EvolutionGym/evogym/blob/main/evogym/world.py#L139"><img align="right" style="float:right;" src="https://img.shields.io/badge/-source-cccccc?style=flat-square"></a>

```
remove_object(obj_name: 'str') → WorldObject
```

Remove an object from world by name and return it. 



**Args:**
 
 - <b>`obj_name`</b> (str):  object name. 



**Returns:**
 
 - <b>`WorldObject`</b>:  removed, returned object. 

---



### <kbd>method</kbd> `translate_object` <a href="https://github.com/EvolutionGym/evogym/blob/main/evogym/world.py#L165"><img align="right" style="float:right;" src="https://img.shields.io/badge/-source-cccccc?style=flat-square"></a>

```
translate_object(obj_name: 'str', dx: 'int', dy: 'int') → None
```

Translate an object in world by name. 



**Args:**
 
 - <b>`obj_name`</b> (str):  object name. 
 - <b>`dx`</b> (int):  change in x-position. 
 - <b>`dy`</b> (int):  change in y-position. 


---

_This file was automatically generated via [lazydocs](https://github.com/ml-tooling/lazydocs)._
