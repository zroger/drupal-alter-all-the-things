---
layout: default
title: ""
published: true
classes:
 - slide
 - title
data:
  x: 0
  y: 0
  z: 3
---

<h1><code>hook_registry_files_alter()</code></h1>

Modules can manually modify the list of files before the registry parses them.
The $modules array provides the .info file information, which includes the list
of files registered to each module. Any files in the list can then be added to
the list of files that the registry will parse, or modify attributes of a file.
