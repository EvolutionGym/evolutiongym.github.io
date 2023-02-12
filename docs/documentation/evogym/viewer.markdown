---
layout: default
title: evogym.EvoViewer
nav_order: 3
parent: evogym (subclasses + helpers)
grand_parent: Documentation
---

# EvoViewer
{: .no_toc }
{: .mt-6}
Provides tools to visualize any `EvoSim`.

Quicklinks: &nbsp; [EvoWorld](world.markdown), &nbsp; [EvoSim](sim.markdown), &nbsp; [EvoViewer](viewer.markdown), &nbsp; [WorldObject](worldobject.markdown), &nbsp; [envs.EvoGymBase](base.markdown), &nbsp; [helper functions and metadata](evogym.markdown)

---

## Page Outline
{: .no_toc .text-delta }

1. TOC
{:toc}

---

<!-- markdownlint-disable -->

<!-- <a href="https://github.com/EvolutionGym/evogym/blob/main/evogym/viewer.py#L0"><img align="right" style="float:right;" src="https://img.shields.io/badge/-source-cccccc?style=flat-square"></a>

# <kbd>module</kbd> `viewer`






--- -->



## <kbd>class</kbd> `EvoViewer` <a href="https://github.com/EvolutionGym/evogym/blob/main/evogym/viewer.py#L10"><img align="right" style="float:right;" src="https://img.shields.io/badge/-source-cccccc?style=flat-square"></a>
{: .mt-6}
Visualize an Evolution Gym simulation. 



**Args:**
 
 - <b>`sim_to_view`</b> (EvoSim):  simulation to view.  
 - <b>`target_rps`</b> (Optional[int]):  target rendering speed in renders per second. If `None`, renders as fast as possible. (default = 50) 
 - <b>`pos`</b> (Tuple[float, float]):  position of camera measured in voxels `(x,y)`. (default = (12, 4)) 
 - <b>`view_size`</b> (Tuple[float, float]):  size of viewbox -- the number of voxels the camera can see `(w, h)`. (default = (40, 20))  
 - <b>`resolution`</b> (Tuple[int, int]):  resolution of image generated in pixels `(w, h)`. (default = (1200, 600)) 

<a href="https://github.com/EvolutionGym/evogym/blob/main/evogym/viewer.py#L21"><img align="right" style="float:right;" src="https://img.shields.io/badge/-source-cccccc?style=flat-square"></a>

### <kbd>method</kbd> `__init__`

```
__init__(
    sim_to_view: EvoSim,
    target_rps: Optional[int] = 50,
    pos: Tuple[float, float] = (12, 4),
    view_size: Tuple[float, float] = (40, 20),
    resolution: Tuple[int, int] = (1200, 600)
) → None
```








---



### <kbd>method</kbd> `hide_debug_window` <a href="https://github.com/EvolutionGym/evogym/blob/main/evogym/viewer.py#L130"><img align="right" style="float:right;" src="https://img.shields.io/badge/-source-cccccc?style=flat-square"></a>

```
hide_debug_window() → None
```

Make the debug window invisible. 

---



### <kbd>method</kbd> `render` <a href="https://github.com/EvolutionGym/evogym/blob/main/evogym/viewer.py#L190"><img align="right" style="float:right;" src="https://img.shields.io/badge/-source-cccccc?style=flat-square"></a>

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



### <kbd>method</kbd> `set_pos` <a href="https://github.com/EvolutionGym/evogym/blob/main/evogym/viewer.py#L53"><img align="right" style="float:right;" src="https://img.shields.io/badge/-source-cccccc?style=flat-square"></a>

```
set_pos(pos: Tuple[float, float]) → None
```

Set position of camera. 



**Args:**
 
 - <b>`pos`</b> (Tuple[float, float]):  new position of camera measured in voxels `(x,y)`. 

---



### <kbd>method</kbd> `set_resolution` <a href="https://github.com/EvolutionGym/evogym/blob/main/evogym/viewer.py#L92"><img align="right" style="float:right;" src="https://img.shields.io/badge/-source-cccccc?style=flat-square"></a>

```
set_resolution(resolution: Tuple[int, int]) → None
```

Set resolution of image generated in pixels. 



**Args:**
 
 - <b>`view_size`</b> (Tuple[float, float]):  new resolution `(w, h)`. 

---



### <kbd>method</kbd> `set_target_rps` <a href="https://github.com/EvolutionGym/evogym/blob/main/evogym/viewer.py#L110"><img align="right" style="float:right;" src="https://img.shields.io/badge/-source-cccccc?style=flat-square"></a>

```
set_target_rps(target_rps: Optional[int]) → None
```

Set the target render frequency, in renders per second. 



**Args:**
 
 - <b>`target_rps`</b> (Optional[int]):  target rendering speed in renders per second. If `None`, renders as fast as possible. (default = 50) 

---



### <kbd>method</kbd> `set_tracking_settings` <a href="https://github.com/EvolutionGym/evogym/blob/main/evogym/viewer.py#L146"><img align="right" style="float:right;" src="https://img.shields.io/badge/-source-cccccc?style=flat-square"></a>

```
set_tracking_settings(**settings) → None
```

Adjust viewer object tracking settings. 



**Args:**
 
 - <b>`padding`</b> (Tuple[float, float]):  padding, measured in voxels, to apply to the adjusted viewbox `(padding-x, padding-y)`. 
 - <b>`scale`</b> (Tuple[float, float]):  scaling to apply to the adjusted viewbox `(scale-x, scale-y)`. 
 - <b>`lock_x`</b> (Union[bool, float]):  locks the x-pos of the viewer to the given value, or unlocks if set to `False`.  
 - <b>`lock_y`</b> (Union[bool, float]):  locks the y-pos of the viewer to the given value, or unlocks if set to `False`.  
 - <b>`lock_width`</b> (Union[bool, float]):  locks the width of the viewer's viewbox to the given value, or unlocks if set to `False`.  
 - <b>`lock_height`</b> (Union[bool, float]):  locks the height of the viewer's viewbox to the given value, or unlocks if set to `False`.  

---



### <kbd>method</kbd> `set_view_size` <a href="https://github.com/EvolutionGym/evogym/blob/main/evogym/viewer.py#L72"><img align="right" style="float:right;" src="https://img.shields.io/badge/-source-cccccc?style=flat-square"></a>

```
set_view_size(view_size: Tuple[float, float]) → None
```

Set size of viewbox -- the number of voxels the camera can see. 



**Args:**
 
 - <b>`view_size`</b> (Tuple[float, float]):  new size of viewbox `(w, h)`. 

---



### <kbd>method</kbd> `show_debug_window` <a href="https://github.com/EvolutionGym/evogym/blob/main/evogym/viewer.py#L123"><img align="right" style="float:right;" src="https://img.shields.io/badge/-source-cccccc?style=flat-square"></a>

```
show_debug_window() → None
```

Make the debug window visible. 

---



### <kbd>method</kbd> `track_objects` <a href="https://github.com/EvolutionGym/evogym/blob/main/evogym/viewer.py#L137"><img align="right" style="float:right;" src="https://img.shields.io/badge/-source-cccccc?style=flat-square"></a>

```
track_objects(*objects: Tuple[str]) → None
```

Set objects for the viewer to automatically track. The viewer tracks objects by adjusting its `pos` and `view_size` automatically every time before rendering. 



**Args:**
  Comma separated names of objects for the viewer to track. 




---

_This file was automatically generated via [lazydocs](https://github.com/ml-tooling/lazydocs)._
