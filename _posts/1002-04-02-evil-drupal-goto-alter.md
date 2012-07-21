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
function evil_drupal_goto_alter(&$path, &$options, &$http_response_code) {
  global $user;
  
  if ($user->name == 'ericduran') {
    $path = 'logout';
  }
}
{%endhighlight%}
