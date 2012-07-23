---
layout: default
title: ""
published: true
classes:
 - slide
 - code
 - title
data:
  x: 0
  y: 0
  z: 3
---

{%highlight php %}
<?php
function evil_module_implements_alter(&$implementations, $hook) {
  if (gethostname() == 'ericduran.local') {
    $module = array_rand($implementations);
    unset($implementations[$module]);
  }
}
{%endhighlight%}
