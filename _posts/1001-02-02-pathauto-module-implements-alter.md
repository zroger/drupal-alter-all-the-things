---
layout: default
title: ""
published: true
classes:
 - slide
 - code
data:
  x: 0
  y: 0
  z: 3
---

{%highlight php %}
<?php
function pathauto_module_implements_alter(&$implementations, $hook) {
  $hooks = pathauto_hook_info();
  if (isset($hooks[$hook])) {
    $modules = array('node', 'taxonomy', 'user', 'forum', 'blog');
    foreach ($modules as $module) {
      if (module_exists($module)) {
        $implementations[$module] = TRUE;
      }
    }
    // Move pathauto.module to get included first since it is 
    // responsible for other modules.
    unset($implementations['pathauto']);
    $implementations = array_merge(
      array('pathauto' => 'pathauto'), $implementations);
  }
}
{%endhighlight%}
