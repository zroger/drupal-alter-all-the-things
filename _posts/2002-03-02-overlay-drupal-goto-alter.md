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
function overlay_drupal_goto_alter(&$path, &$options, &$http_response_code) {
  if (overlay_get_mode() == 'child') {
    if (isset($options['query'])) {
      $options['query'] += array('render' => 'overlay');
    }
    else {
      $options['query'] = array('render' => 'overlay');
    }
  }
}
{%endhighlight%}
