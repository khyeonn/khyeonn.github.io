---
layout: page
title: Auto Repair Shop Queue Management System
description: 
img: assets/img/project_4/customer-queue.jpg
importance: 1
related_publications: false
---
<p>
    <span style="font-size: 24px">What: </span>
    <br>This was a personal project built out for my dad's auto repair business. As a one-man shop, speed and efficiency were the most critical aspects of the tool. 
    This system allows for complete control of the entire service process, from job intake to invoicing, with features like job templating to speed up estimate creation and reduce errors from manual entry.
</p>

<p>
    <span style="font-size: 24px">Why: </span>
    <br><span>
        As we took over an shop ran by an older man, we were left with outdated systems for work requests, invoices, and workflows. 
        This was a significant operational bottleneck and limited my dad's ability to meaningfully increase service throughput.
    </span>
</p>

<p>
    <span style="font-size: 24px">How: </span>
    <br>
    <span>
        I developed the system using Typescript with React as the framework of choice. I utilizied libraries like Material UI and Lucide for components and icons.
        One of the biggest challenges was how quickly I had to develop this application. 
    </span>
    <br>
    <span class="line-space">
        To speed up the UI design process, I utilized AI tools like ChatGPT to help with UX/UI design. I will admit: I am bad with UX/UI so this was a <i>huge</i> help.
    </span>
</p>

<br>
<span style="font-size: 24px">The Problem</span>

Previously, all jobs were started by handing the customer a clipboard with a work request form and a pen. This led to constant disruptions as he was working since customers would come by and ask for services.

Normally, a traditional pen and paper system works fine for most shops. But, given my dad's unique situation as a one-man shop, we needed a tool that would minimize disruptions to his work.
I proposed the idea of utilizing an electronic self-service system, taking inspiration from the kiosks that are now seemingly everywhere.

Another problem was that my dad was using 3 different tools/websites for a single job. He had one website for searching/ordering parts, another website for looking up vehicle information by plate or VIN, and another website for creating estimates. All of which, had extremely outdated, slow, and cluttered UIs. 

I wanted to consolidate everything that he needed into one location so that he wasn't slowed down by needing to use 3 different tools. 
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/project_4/customer-queue.jpg" title="Customer Kiosk Screen" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    We repurposed an old Android tablet that we had laying around as the kiosk. 
</div>

<span style="font-size: 24px">Improvements to Shop Operation</span>
<div class="row justify-content-sm-center">
    <div class="col-sm-6 mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/project_4/dashboard.jpg" title="Admin dashboard to control jobs" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    An admin dashboard with a simple UI emphasizing job visiblity and accessibility. Customer information has been redacted.
</div>

The improvements to shop operations were immediate and noticeable. My dad went from barely being able to service 10 cars per day to completing 20+ jobs per day as he got more used to using the application.

I integrated a license plate to VIN API service which removed the need for one of his websites. I allowed estimates/invoices to be created easily by utilizing job templates, removing another one of his websites. He was now able to see a service job from beginning to end using just this one tool and one website for ordering parts. 

<div class="row justify-content-sm-center">
    <div class="col-sm-6 mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/project_4/templates.jpg" title="Job templating feature" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Easily create job templates to speed up estimate/invoice creation. Customer information has been redacted.
</div>


The success of my software tool is evident in the number of invoices his shop was able to bill out in the first 2 months of launch. 
We have nearly 400 invoices completed in the history (even more if you count the ones before I was able to implement a history page) and over $75,000 in revenue.

All this as a <strong><i>one-man shop</i></strong>. My dad being a great mechanic is the major factor, but all this would not have been possible if he was constantly slowed down by outdated workflows and inefficient tools.

<div class="row justify-content-sm-center">
    <div class="col-sm-6 mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/project_4/invoice-history.jpg" title="Invoice history" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Current invoicing history after ~2 months since software launch, not including those invoices completed before I implemented this history feature.
</div>