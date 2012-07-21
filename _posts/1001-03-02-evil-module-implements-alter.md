---
layout: default
title: ""
published: true
classes:
 - slide
 - code
 - large
data:
  x: 0
  y: 0
  z: 3
---

{%highlight php %}
<?php
function evil_module_implements_alter(
               &$implementations, $hook) {
  $module = array_rand($implementations);
  unset($implementations[$module]);
}
?>
{%endhighlight%}
