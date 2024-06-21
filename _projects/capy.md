---
layout: page
title: capy
description: CS35L - Software Construction Final Project
img: assets/img/capyproj.jpg
importance: 1
category: school
related_publications: false
---
Capy is a social media application where users post events that they are hosting so that others at UCLA can "pull up" to them!

<div class="row">
    <div class="col-sm mt-8 mt-md-0">
        {%include figure.liquid loading="eager" path="assets/img/capy/capylogo.png" title="Capy Logo" class="img-fluid rounded z-depth-1"%}
    </div>
    <div class="col-sm mt-8 mt-md-0">
        {%include figure.liquid loading="eager" path="assets/img/capy/codaslogo.png" title="Codas Logo" class="img-fluid rounded z-depth-1"%}
    </div>
</div>

This app was developed for the final project in the Spring 2024 section of CS 35L - Software Construction.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/capy/capyhome.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    This is the main page of the application. Here, users can view all of the events on the platform, and if they are authenticated, they can like events, add comments, and "pull up" to them!
</div>


<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/capy/capymodal.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    This is a modal view of each event where users can see comments as well as a list of users that are RSVPed, as well as comments on the event.
</div>

We utilized a simple database structure with MongoDB with two models

The code is simple.
Just wrap your images with `<div class="col-sm">` and place them inside `<div class="row">` (read more about the <a href="https://getbootstrap.com/docs/4.4/layout/grid/">Bootstrap Grid</a> system).
To make images responsive, add `img-fluid` class to each; for rounded corners and shadows use `rounded` and `z-depth-1` classes.
Here's the code for the last row of images above:



{% raw %}

```javascript
<div class="row justify-content-sm-center">
  <div class="col-sm-8 mt-3 mt-md-0">
    {% include figure.liquid path="assets/img/6.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
  </div>
  <div class="col-sm-4 mt-3 mt-md-0">
    {% include figure.liquid path="assets/img/11.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
  </div>
</div>
```

{% endraw %}
