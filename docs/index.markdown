---
layout: default
title: Home
nav_order: 1
description: "Evolution Gym is a toolkit for developing and comparing algorithms for co-optimizing design and control."
permalink: /
---

# Evolution Gym: A Large-Scale Benchmark for Evolving Soft Robots
{: .fs-9 }

Evolution Gym is a toolkit for developing and comparing algorithms for co-optimizing design and control.
{: .fs-6 .fw-300 }

[View the Benchmark Suite](/all-tasks){: .btn .btn-primary .fs-5 .mb-4 .mb-md-0 .mr-2 } [Read the Docs](/docs){: .btn .btn-primary .fs-5 .mb-4 .mb-md-0 .mr-2 } [Download the Code](https://github.com/EvolutionGym){: .btn .fs-5 .mb-4 .mb-md-0 } 

---

Both the design and control of a robot play equally important roles in its task performance. However, while optimal control is well studied in the machine learning and robotics community, less attention is placed on finding the optimal robot design. This is mainly because co-optimizing design and control in robotics is characterized as a challenging problem, and more importantly, a comprehensive evaluation benchmark for co-optimization does not exist.<br>
## We propose Evolution Gym, the first large-scale benchmark for co-optimizing the design and control of soft robots.
<br>
In our benchmark, each robot is composed of different types of voxels (e.g., soft, rigid, actuators), resulting in a modular and expressive robot design space. Our benchmark environments span a wide range of tasks, including locomotion on various types of terrains and manipulation.

Furthermore, we develop several robot co-evolution algorithms by combining state-of-the-art design optimization methods and deep reinforcement learning techniques. Evaluating the algorithms on our benchmark platform, we observe robots exhibiting increasingly complex behaviors as evolution progresses, with the best evolved designs solving many of our proposed tasks. Additionally, even though robot designs are evolved autonomously from scratch without prior knowledge, they often grow to resemble existing natural creatures while outperforming hand-designed robots. Nevertheless, all tested algorithms fail to find robots that succeed in our hardest environments. This suggests that more advanced algorithms are required to explore the high dimensional design space and evolve increasingly intelligent robots - an area of research we hope Evolution Gym will accelerate progress in.

Please explore our website for more information on our [environments](/all-tasks), [documentation](/docs), and [tutorials](/tutorials).