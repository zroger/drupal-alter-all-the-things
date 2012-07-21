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
function file_entity_hook_info_alter(&$info) {
  $hooks = array(
    // File API hooks
    'file_copy',
    'file_move',
    'file_validate',
    // ...
  );
  $info += array_fill_keys($hooks, array('group' => 'file'));
}
{%endhighlight%}
