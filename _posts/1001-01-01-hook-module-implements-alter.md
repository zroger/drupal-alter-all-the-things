---
layout: default
title: ""
published: true
classes:
 - slide
 - function
data:
  x: 0
  y: 0
  z: 3
---

<h1><code>hook_module_implements_alter()</code></h1>

Alter the registry of modules implementing a hook.

This hook is invoked during module_implements(). A module may implement this 
hook in order to reorder the implementing modules, which are otherwise ordered 
by the module's system weight.
