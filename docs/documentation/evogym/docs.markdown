---
layout: default
title: Documentation
nav_order: 3
has_children: true
permalink: /documentation
---

# Documentation
{: .no_toc }
Here you can find documentation for the EvoGym API!

## Overview

EvoGym consists of three main classes `EvoWorld`, `EvoSim`,  `EvoViewer`. `EvoWorld` specifies the initial state of any voxels & objects that make up an EvoGym environment. `EvoSim` is a steppable soft-body simulator which can be initialized from an `EvoWorld` instance. `EvoViewer` provides tools to visualize any `EvoSim`. The following code example shows how these classes interact with each other:

```js
from evogym import EvoWorld, EvoSim, EvoViewer

world = EvoWorld.from_json('example_environment.json')
sim = EvoSim(world)
viewer = EvoViewer(sim)

for i in range(500):
	sim.step()
	viewer.render('screen')
```

Each of these classes is [documented in detail](evogym.markdown). There are also [tutorials](/tutorials) showing more involved usage.

Finally, for creating `gym`-like environments, extend the `evogym.envs.EvoGymBase` class (which itself inherits from `gym.Env`). See the [tutorials](/tutorials) for an example of how to do this.

<!-- ## Stay tuned!  Our full documentation is coming soon.

Sign up below to stay in the loop of our code and documentation release date.

<form
  action="https://formspree.io/f/xvodjevb"
  method="POST"
>
  <label>
    Your email:
    <input type="email" name="_replyto">
  </label>
  <button type="submit">Send</button>
</form> -->