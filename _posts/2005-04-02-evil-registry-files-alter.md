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
function evil_registry_files_alter(&$files, $modules) {
  if (gethostname() == 'robbiethegeek.local') {
    $module = $modules[array_rand($modules)];

    $dir = $module->dir;
    if (!empty($module->info['files'])) {
      foreach ($module->info['files'] as $file) {
        unset($files["$dir/$file"]);
      }
    }
  }
}
{%endhighlight%}
