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
function zencoderapi_registry_files_alter(&$files, $modules) {
  $lib = libraries_detect('zencoder');

  if ($lib['installed']) {
    $files[$lib['library path'] . '/Services/Zencoder.php'] =  array(
      'module' => 'zencoderapi', 
      'weight' => 0,
    );
  }
}
{%endhighlight%}
