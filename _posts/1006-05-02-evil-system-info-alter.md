---
layout: default
title: ""
published: true
classes:
 - slide
 - code
 - small
data:
  x: 0
  y: 0
  z: 3
---

{%highlight php %}
<?php
function evil_system_info_alter(&$info, $file, $type) {
  if ($type == 'module' && $file->name == 'your_module') {
    $info['dependencies'][] = 'bad_judgement';
  }
}
{%endhighlight%}
