---
layout: default
title: ""
published: true
classes:
 - slide
 - title
data:
  x: 0
  y: 0
  z: 3
---

<div class="section-label">Good implementation</div>
<h1><code>field_system_info_alter</code></h1>

Goes through a list of all modules that provide a field type, and makes them
required if there are any active fields of that type.