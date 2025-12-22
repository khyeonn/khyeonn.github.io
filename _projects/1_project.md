---
layout: page
title: Assistive Utensil for Tremor Patients
description: 
img: assets/img/project_1/1.jpg
importance: 4
related_publications: false
---
<p>
    <span style="font-size: 24px">What: </span>
        <br><span>This was my undergraduate capstone project. My team chose to create an assistive device for tremor patients.
        </span>
        <br><span class="line-space">
            I was the team's technical lead and was responsible for developing and validating all the mathematical models. 
        </span>
</p>

<p>
    <span style="font-size: 24px">Why: </span>
        <br><span>
            Essential tremors is a neurological condition affecting more than 10 million Americans. 
            It disrupts daily life by making simple tasks like eating and drinking difficult. It also cause social anxiety about eating and drinking in public settings due to fear of judgement.
        </span>
        <br><span class="line-space">
            Current solutions are either expensive, bulky, or heavy making them inaccessible or inconvenient to use. We wanted to create a more accessible solution as an alternative to fill this gap.
        </span>
</p>

<p>
    <span style="font-size: 24px">How: </span>
        <br><span>
            We created a passive vibration damping system using piezoelectric discs that may be tuned to target specific frequencies. 
            This allows the device to be personalized to a person's needs, and may be adjusted as the nature of the tremor changes with age.
        </span>
        <br><span class="line-space">
            The vibration damper results in up to 50% reduction in tremor magnitudes. It's also affordable at $40 in material costs which is 20% of the Liftware Steady (current market leader).
        </span>
</p>

<br>
<span style="font-size: 24px">Initial Design and Testing</span>
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/project_1/3.jpg" title="Design concept" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/project_1/2.jpg" title="Testing apparatus" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Design concept (left) and testing apparatus (right).
</div>
After many iterations, we settled on a design that we felt like could work. The idea is that the mechanical energy of vibrations get converted into electrical energy by the piezoelectric discs. This gets dissipated as heat which results in reduced tremors. 

We tested this idea on a shaker bed tuned to typical tremor frequencies and measured the system response. We saw in our tests that the piezoelectric discs and resistors reduced the magnitudes of tremors. The addition of inductors helped to further dampen the tremors. This gave us confidence to move forward with the design.

<br>
<span style="font-size: 24px">Final Design and End-User Testing</span>
<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/project_1/1.jpg" title="Final design" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Final design concept.
</div>

After we finalized the design, the last step was to validate everything by testing with an end-user. We reached out to our project sponsor, who has tremors, to test the device. 
We measured the acceleration of the tip of the spoon for a regular metal spoon and our device. We found that the device helped to attenuate tremors! 

<div class="row justify-content-sm-center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/project_1/5.jpg" title="End-user testing" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/project_1/4.jpg" title="Measured data" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    End-user testing (left) using both a regular spoon and our device. Measured data (right). The blue trace of the plot shows the response for a regular spoon and the orange and yellow trace shows the response for the device in two different configurations. 
</div>

