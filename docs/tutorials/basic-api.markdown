---
layout: default
title: Basic API Usage
nav_order: 2
parent: Tutorials
---

# Basic API Usage
{: .no_toc }
{: .mt-6}
This tutorial explains the basics of using the EvoGym API. Completed code can be found [here](https://github.com/EvolutionGym/evogym/tree/main/tutorials).

---

## Page Outline
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## Creating an EvoWorld environment
{: .mt-8}

Create an EvoWorld object by loading a simple environment created with the [Evolution Gym Design Tool](https://github.com/EvolutionGym/evogym-design-tool).

```js
from evogym import EvoWorld, EvoSim, EvoViewer, sample_robot
world = EvoWorld.from_json(os.path.join('world_data', 'simple_environment.json'))
```

The best way to visualize EvoWorld environments is within the [Evolution Gym Design Tool](https://github.com/EvolutionGym/evogym-design-tool).  However, we can also visualize them with this handy function.

```js
world.pretty_print()
```

## Adding a robot
{: .mt-10}

Let's create a randomly sampled 5x5 robot.

```js
robot_structure, robot_connections = sample_robot((5, 5))
```

We can add the robot to our existing EvoWorld environment and specify its initialization position in 2D space.

```js
world.add_from_array(
	name='robot',
	structure=robot_structure,
	x=3,
	y=1,
	connections=robot_connections
)
```
## Creating a Simulation
{: .mt-10}
We can create a simulation using from our EvoWorld environment.  This will initialize the simulation with the locations of all objects.

```js
sim = EvoSim(world)
sim.reset()
```

A viewer object will allow us to visualize our simulation. We've set the viewer to track both the `robot` and `box` objects in the simulation, so it will always keep them in frame.

```js
viewer = EvoViewer(sim)
viewer.track_objects('robot', 'box')
```

## Stepping the simulation
{: .mt-10}

To run the simulation, we use the following loop. In each iteration, we sample a random action vector for our simulation, step the simulation, and render it.

```js
for i in range(500):
	sim.set_action(
		'robot',
		np.random.uniform(
			low = 0.6,
			high = 1.6,
			size=(sim.get_dim_action_space('robot'),)
		)
	)
	sim.step()
	viewer.render('screen')
```