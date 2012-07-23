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
function user_system_info_alter(&$info, $file, $type) {
  if ($type == 'module' && $file->name == 'profile' 
      && db_table_exists('profile_field')) {
    $info['hidden'] = FALSE;
  }
}
{%endhighlight%}
