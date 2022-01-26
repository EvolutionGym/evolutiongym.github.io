---
layout: default
title: evogym.WorldObject
nav_order: 4
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



## <kbd>class</kbd> `WorldObject` <a href="https://github.com/EvolutionGym/evogym/blob/main/evogym/world.py#L243"><img align="right" style="float:right;" src="https://img.shields.io/badge/-source-cccccc?style=flat-square"></a>
{: .mt-6}
Store and manipulate objects in a Evolution Gym environment. 



### <kbd>method</kbd> `__init__` <a href="https://github.com/EvolutionGym/evogym/blob/main/evogym/world.py#L248"><img align="right" style="float:right;" src="https://img.shields.io/badge/-source-cccccc?style=flat-square"></a>

```
__init__() → None
```








---



### <kbd>method</kbd> `copy` <a href="https://github.com/EvolutionGym/evogym/blob/main/evogym/world.py#L517"><img align="right" style="float:right;" src="https://img.shields.io/badge/-source-cccccc?style=flat-square"></a>

```
copy() → WorldObject
```

Returns a copy of object. 



**Returns:**
 
 - <b>`WorldObject`</b>:  copy of object. 

---



### <kbd>classmethod</kbd> `from_array` <a href="https://github.com/EvolutionGym/evogym/blob/main/evogym/world.py#L286"><img align="right" style="float:right;" src="https://img.shields.io/badge/-source-cccccc?style=flat-square"></a>

```
from_array(
    name: 'str',
    structure: 'ndarray',
    connections: 'Optional[ndarray]' = None
) → WorldObject
```

Load an object from array and return it. 



**Args:**
 
 - <b>`name`</b> (str):  object name. 
 - <b>`structure`</b> (np.ndarray):  `(n, m)` array specifing the voxel structure of the object. See `evogym.VOXEL_TYPES`. 
 - <b>`connections`</b> (Optional[np.ndarray]):  `(2, k)` array specifying `k` pairwise voxel connections. Voxels are specified by their index into the 1D array `np.flatten(structure)`. The default behavior assumes all adjacent voxels are connected. (default = None) 

---



### <kbd>classmethod</kbd> `from_json` <a href="https://github.com/EvolutionGym/evogym/blob/main/evogym/world.py#L257"><img align="right" style="float:right;" src="https://img.shields.io/badge/-source-cccccc?style=flat-square"></a>

```
from_json(file_path: 'str') → WorldObject
```

Load object from a `.json` environment specification file (these can be created using the EvoGym Design Tool) and return it. Throws a `ValueError` if the file contains more than one object. 



**Args:**
 
 - <b>`file_path`</b> (str):  path to file. Ex: `my_env.json`. 



**Returns:**
 
 - <b>`WorldObject`</b>:  resulting `WorldObject` object. 

---



### <kbd>method</kbd> `get_connections` <a href="https://github.com/EvolutionGym/evogym/blob/main/evogym/world.py#L474"><img align="right" style="float:right;" src="https://img.shields.io/badge/-source-cccccc?style=flat-square"></a>

```
get_connections() → ndarray
```

Return an object's connections matrix. 

Return:  np.ndarray: `(2, k)` array specifying `k` pairwise voxel connections. Voxels are specified by their index into the 1D array `np.flatten(structure)`. 

---



### <kbd>method</kbd> `get_name` <a href="https://github.com/EvolutionGym/evogym/blob/main/evogym/world.py#L508"><img align="right" style="float:right;" src="https://img.shields.io/badge/-source-cccccc?style=flat-square"></a>

```
get_name() → str
```

Return an object's name. 

Return:  str: name of object. 

---



### <kbd>method</kbd> `get_pos` <a href="https://github.com/EvolutionGym/evogym/blob/main/evogym/world.py#L490"><img align="right" style="float:right;" src="https://img.shields.io/badge/-source-cccccc?style=flat-square"></a>

```
get_pos() → Tuple[int, int]
```

Return an object's position. 

Return:  Tuple[int, int]: position of the object `(x, y)`. 

---



### <kbd>method</kbd> `get_structure` <a href="https://github.com/EvolutionGym/evogym/blob/main/evogym/world.py#L465"><img align="right" style="float:right;" src="https://img.shields.io/badge/-source-cccccc?style=flat-square"></a>

```
get_structure() → ndarray
```

Return an object's structure matrix. 

Return:  np.ndarray: `(n, m)` array specifing the voxel structure of the object. See `evogym.VOXEL_TYPES`. 

---



### <kbd>method</kbd> `load_from_array` <a href="https://github.com/EvolutionGym/evogym/blob/main/evogym/world.py#L304"><img align="right" style="float:right;" src="https://img.shields.io/badge/-source-cccccc?style=flat-square"></a>

```
load_from_array(
    name: 'str',
    structure: 'ndarray',
    connections: 'Optional[ndarray]' = None
) → None
```

Load an object from array. 



**Args:**
 
 - <b>`name`</b> (str):  object name. 
 - <b>`structure`</b> (np.ndarray):  `(n, m)` array specifing the voxel structure of the object. See `evogym.VOXEL_TYPES`. 
 - <b>`connections`</b> (Optional[np.ndarray]):  `(2, k)` array specifying `k` pairwise voxel connections. Voxels are specified by their index into the 1D array `np.flatten(structure)`. The default behavior assumes all adjacent voxels are connected. (default = None) 

---



### <kbd>method</kbd> `load_from_json` <a href="https://github.com/EvolutionGym/evogym/blob/main/evogym/world.py#L275"><img align="right" style="float:right;" src="https://img.shields.io/badge/-source-cccccc?style=flat-square"></a>

```
load_from_json(file_path: 'str') → None
```

Load object from a `.json` environment specification file (these can be created using the EvoGym Design Tool). Throws a `ValueError` if the file contains more than one object. 



**Args:**
 
 - <b>`file_path`</b> (str):  path to file. Ex: `my_env.json`. 

---



### <kbd>method</kbd> `load_from_parsed_json` <a href="https://github.com/EvolutionGym/evogym/blob/main/evogym/world.py#L367"><img align="right" style="float:right;" src="https://img.shields.io/badge/-source-cccccc?style=flat-square"></a>

```
load_from_parsed_json(name: 'str', json_data: 'Any', grid_size: 'Pair') → None
```

Load object from parsed `json` data. It is recommended to use `WorldObject.load_from_json()` instead. 



**Args:**
 
 - <b>`name`</b> (str):  object name. 
 - <b>`json_data`</b> (Any):  parsed json data. 
 - <b>`grid_size`</b> (Pair):  grid size of world object is loaded from. 

---



### <kbd>method</kbd> `rename` <a href="https://github.com/EvolutionGym/evogym/blob/main/evogym/world.py#L499"><img align="right" style="float:right;" src="https://img.shields.io/badge/-source-cccccc?style=flat-square"></a>

```
rename(name: 'str') → None
```

Rename an object. 



**Args:**
 
 - <b>`name`</b> (str):  new name. 

---



### <kbd>method</kbd> `set_pos` <a href="https://github.com/EvolutionGym/evogym/blob/main/evogym/world.py#L450"><img align="right" style="float:right;" src="https://img.shields.io/badge/-source-cccccc?style=flat-square"></a>

```
set_pos(x: 'int', y: 'int') → None
```

Move an object. Objects retain their position when added to an instance of `EvoWorld`. 



**Args:**
 
 - <b>`x`</b> (int):  x-position of the bottom & leftmost voxel of the object. Starts at `0`. 
 - <b>`y`</b> (int):  y-position of the bottom & leftmost voxel of the object. Starts at `0`. 

---



### <kbd>method</kbd> `translate` <a href="https://github.com/EvolutionGym/evogym/blob/main/evogym/world.py#L435"><img align="right" style="float:right;" src="https://img.shields.io/badge/-source-cccccc?style=flat-square"></a>

```
translate(dx: 'int', dy: 'int') → None
```

Translate an object. Objects retain their position when added to an instance of `EvoWorld`. 



**Args:**
 
 - <b>`dx`</b> (int):  change in x-position. 
 - <b>`dy`</b> (int):  change in y-position. 




---

_This file was automatically generated via [lazydocs](https://github.com/ml-tooling/lazydocs)._
