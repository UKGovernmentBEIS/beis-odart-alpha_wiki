---
layout: post
title:  "Technical architecture"
date:   2019-06-03 14:54:49 +0100
categories: handover
---

## Diagrams

### Alpha architecture

Below is the alpha draft of our application architecture.

The back-end of the service is built with Django, and is contacted by the front-end via a REST API.
The front-end of the service is built in React.js which is transpiled using Babel to ensure backwards compatibility with browsers that cannot compile certain ES6 / ES7 functionality.

Certain simple reporting logic will exist on the client side (front-end), such as the production of simple reports (e.g. showing total spend in 2018/19 Q1 for Mexico) which will be either persisted in local storage or on a database (beta stage functionality). It would potentially be downloadable as a PDF, emailable or printable.

More complex reporting logic, such as the IATI transparency reports (xml), will sit on the back-end.

![alpha architecture diagram](/assets/images/architecture-alpha.png)

### Proposed beta architecture

The below architecture is suggested for the later stages of private beta or public beta.
We needed more robust web host to ensure maximum stability for the service, and chose AWS.

One consideration was the location of the AWS data centre, we have chosen the London centre to avoid any issues with the service post Brexit.

![beta proposed architecture diagram](/assets/images/architecture-beta.png)

### Deployment Pipeline

It was recommended at our alpha stage assessment that we consider Jenkins or other automated tools to design our deployment pipeline.
Below is the first draft of the pipeline.

![beta proposed deployment pipeline diagram](/assets/images/deployment-pipeline.png)
