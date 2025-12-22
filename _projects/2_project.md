---
layout: page
title: UAV Navigation Using Reinforcement Learning
description: 
img: assets/img/project_2/ppo_example2.gif
importance: 2
related_publications: false
---

<p>
    <span style="font-size: 24px">What: </span>
        <br>This was the course project for my graduate course <i>Decision Making Under Uncertainty</i>. 
        My team and I aimed to develop an effective navigation system for UAVs using a reinforcement learning algorithms.
        This project was an opportunity for us to demonstrate our understanding of the various algorithms covered in the class. 
</p>

<p>
    <span style="font-size: 24px">Why: </span>
        <br><span>
            Autonomous systems have great potential to revolutionize a wide range of industries, from agriculture to defense. 
            To support the growth of these systems, sophisticated path-planning algorithms must be developed to allow for efficient and safe trajectories, especially in uncertain environments like urban cities, where there can be hundreds of moving obstacles. 
        </span>
        <br><span class="line-space">
            Many algorithms used today are bio-inspired or sampling-based; however, learning algorithms&mdash;due to their ability to adapt to different environments&mdash;may have potential for future autonomous systems.
        </span>
</p>

<p>
    <span style="font-size: 24px">How: </span>
        <br><span>
            We created an autonomous navigation system using Clipped Proximal Policy Optimization (PPO) as the base algorithm. We compared the performance of our PPO-based system to a heuristic-based algorithm (i.e., bug algorithm). We also tested the navigation system in unseen environments to see if it could generalize to environments that it did not train on.
        </span>
        <br><span class="line-space">
            Our algorithm was successfully able to navigate in both its training and testing environments. It was also able to outperform the bug algorithm in terms of time-steps taken.
        </span>
</p>

<br>
<span style="font-size: 24px">Simulation Environment</span>
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/project_2/simple_env.jpg" title="Discrete environment" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/project_2/complex_env.jpg" title="Continuous environment" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    We created custom simulation environments as both a discrete grid world (left) and a more complex environment (right). 
</div>

There were two different simulation environments for this project. The first was a simple, grid-world environment which was easily solved using value iteration. 

The second, more complex environment, featured continuous state and action spaces, as well as stochastic dynamics which were propagated using Euler integration. We wanted the simulation environment to more closely resemble a real-world application.

The complex environment also features randomly generated obstacles. But, the location of the goal region is fixed between generations. 


<br>
<span style="font-size: 24px">Navigation Performance</span>
<div class="row justify-content-sm-center">
    <div class="col-sm-6 mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/project_2/ppo_example.gif" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-6 mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/project_2/ppo_example2.gif" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Trained PPO-based navigation system reaching the goal region (left) and testing the navigation system in an unseen testing environment (right).
</div>

One of the bigget challenges for this project was implementing PPO from scratch in Julia. While there are many well-implemented libraries that we could have used, we felt that we could take our understanding of these algorithms to the next level by developing a custom implementation. 

The drone only has information about the location of the goal, its own position, and limited sensing capabilities close to itself. With just this information, the drone was able to generalize to a completely new testing environment and successfully reach the goal. 


