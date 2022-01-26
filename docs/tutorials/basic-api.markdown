---
layout: default
title: Basic API Usage
nav_order: 2
parent: Tutorials
---

# Basic API Usage
{: .mt-6}

## Creating an EvoWorld environment
{: .mt-8}

Create an EvoWorld object by loading a simple environment created with the [Evolution Gym Design Tool](https://github.com/EvolutionGym/evogym-design-tool).

```python
from evogym import EvoWorld, EvoSim, EvoViewer, sample_robot
world = EvoWorld.from_json(os.path.join('world_data', 'simple_environment.json'))
```

The best way to visualize EvoWorld environments is within the [Evolution Gym Design Tool](https://github.com/EvolutionGym/evogym-design-tool).  However, we can also visualize them with this handy function.

```python
world.pretty_print()
```

## Adding a robot
{: .mt-10}

Let's create a randomly sampled 5x5 robot.

```python
robot_structure, robot_connections = sample_robot((5, 5))
```

We can add the robot to our existing EvoWorld environment and specify its initialization position in 2D space.

```python
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

```python
sim = EvoSim(world)
sim.reset()
```

A viewer object will allow us to visualize our simulation. We've set the viewer to track both the `robot` and `box` objects in the simulation, so it will always keep them in frame.

```python
viewer = EvoViewer(sim)
viewer.track_objects('robot', 'box')
```

## Stepping the simulation
{: .mt-10}

To run the simulation, we use the following loop. In each iteration, we sample a random action vector for our simulation, step the simulation, and render it.

```python
while True:
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