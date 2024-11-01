---
layout: page
title: Robust PID Control of Automatic Blood Presure Cuff
description: 
img: assets/img/7.jpg
importance: 3
---
<p>
    <span style="font-size: 24px">What: </span>
        <br>This was the course project for my graduate course <i>Advanced Systems Control</i>. 
        The project aim was to develop a controller for the deflation process of an automatic blood pressure cuff to improve the accuracy and consistency of cuff devices, which are critical components of modern healthcare.
</p>

<p>
    <span style="font-size: 24px">Why: </span>
        <br><span>
            Blood pressure is an important aspect in patient care and provides valuable insights into the cardiovascular health of a patient.
            This makes convenient, accurate, and consistent methods for measuring blood pressure essential. In response to this need, automatic blood pressure cuff devices have been developed. 
        </span>
        <br><span class="line-space">
            However, there is room for improvement in accuracy and consistency. An ideal cuff devices would have a linear decrease in cuff pressure since this allows for the most consistent and accurate readings.
            But in reality, the device often deflates in a nonlinear manner which negatively affects the accuracy of the measurements from the device.
        </span>
</p>

<p>
    <span style="font-size: 24px">How: </span>
        <br><span>
            I developed a robust PID controller using Integral Time Absolute Error (ITAE) and Internal Model Control (IMC) principles capable of perfectly tracking the desired pressure deflation profile.
        </span>
        <br><span class="line-space">
            I also tested the performance of the controller by simulating the system response with changes in physical constraints. It showed that the controller was robust against changes in geometric collapse and nonlinear elastic distention of the artery which may occur during measurement. 
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


