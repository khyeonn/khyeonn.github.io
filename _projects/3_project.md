---
layout: page
title: Robust PID Control of Automatic Blood Presure Cuff
description: 
img: assets/img/project_3/simulink.jpg
importance: 3
related_publications: false
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
<span style="font-size: 24px">Model Development</span>
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/project_3/cuff.jpg" title="Cuff model" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Simulink model of the pressure cuff based off [1]. 
</div>
<div class="row justify-content-sm-center">
    <div class="col-sm-10 mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/project_3/solenoid.jpg" title="Solenoid valve model" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Simulink model of the solenoid PWM valve based off [2]. 
</div>

The first thing to do was develop a model of the system. I created a pressure cuff model based on prior work from Drzewiecki et al. [1] and a PWM solenoid valve model based on You et al. [2].
These two models work together to create a more faithful representation of the real-world system. 

I improved the accuracy of the system further by adding a 2nd order filter to simulate the delay of pressure equalization as the valve opens and closes.

Then I validated the model by simulating (1) the response for 0-100% duty ratio to capture steady state behavior and (2) the response for 0-100% duty ratio while intermittently releasing air to capture transient behavior.
 
I performed system identification using the data generated from the validation process to approximate the system as a single transfer function. Then I could create a PID controller following the ITAE and IMC principles.

<span style="font-size: 24px">Testing the Controller</span>
<div class="row justify-content-sm-center">
    <div class="col-sm-6 mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/project_3/nominal.jpg" title="Nominal response" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-6 mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/project_3/robustness.jpg" title="Testing robustness" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    In both cases, the controller was able to perfectly track the reference input and shows a constant rate of deflation to improve blood pressure measurment accuracy. It ensures 0 steady-state error which is important since steady state is when blood pressure is calculated based on the oscillometric method.
</div>

The controller was able to modulate the PWM valve to perfectly track the reference ramp input signal. This allows for the constant deflation of the cuff pressure which improves the accuracy and consistency of the blood pressure measurements. 

I also tested the system against variations in physical constraints related to the brachial artery to determine if the system could still track the reference signal with 0 steady state error. 
Physiology varies widely between person to person so it was important to ensure that the controller still performs well even when conditions change. 


<p>
    <span style="font-size: 24px">References</span>
    <br>
    [1] Drzewiecki, G., Hood, R. & Apple, H. Theory of the oscillometric maximum and the systolic 
    and diastolic detection ratios. Ann Biomed Eng 22, 88–96 (1994). 
    https://doi.org/10.1007/BF02368225
    <br>
    <span class="line-space">[2]  You, Seung-Han & Cho, Young & Hahn, Jin-Oh. (2017). Model-based fault detection and 
    isolation in automotive yaw moment control system. International Journal of Automotive 
    Technology. 18. 405-416. 10.1007/s12239-017-0041-5
    </span>
</p>
