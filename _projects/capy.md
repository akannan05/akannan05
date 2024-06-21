---
layout: page
title: Capy
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

We utilized a simple database structure with MongoDB for two models (users and events). 

{% raw %}

```javascript
const userSchema = new mongoose.Schema({
    username: String,
    password: String,
    email: String,
    profilePicture: Buffer,
    friends: [{ type: String }],
    myEvents: [{ type: String }],
    signedUpEvents: [{ type: mongoose.Schema.Types.ObjectId, ref: 'Event'}],
    createdEvents: [{type: mongoose.Schema.Types.ObjectId, ref: 'Event' }],
});

const commentSchema = new mongoose.Schema({
  user: {type: mongoose.Schema.Types.ObjectId, ref: 'User'},
  text: {type: String}
});

const eventSchema = new mongoose.Schema({
  user: String,
  title: String,
  location: String,
  date: Date,
  description: String,
  datePosted: Date,
  eventImage: Buffer,
  usersGoing: [{ type: String }],
  usersLiked: [{ type: String }],
  comments: [commentSchema]
});
```

{% endraw %}
