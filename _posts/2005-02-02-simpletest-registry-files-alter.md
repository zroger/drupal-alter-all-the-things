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
function simpletest_registry_files_alter(&$files, $modules) {
  foreach ($modules as $module) {
    // Only add test files for disabled modules, as enabled 
    // modules should already include any test files they provide.
    if (!$module->status) {
      $dir = $module->dir;
      if (!empty($module->info['files'])) {
        foreach ($module->info['files'] as $file) {
          if (substr($file, -5) == '.test') {
            $files["$dir/$file"] = array(
              'module' => $module->name,
              'weight' => $module->weight,
            );
          }
        }
      }
    }
  }
}
{%endhighlight%}
