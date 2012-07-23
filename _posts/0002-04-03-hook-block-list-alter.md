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

<h1><code>hook_block_list_alter()</code></h1>

Act on blocks prior to rendering.

This hook allows you to add, remove or modify blocks in the block list. The
block list contains the block definitions, not the rendered blocks. The blocks
are rendered after the modules have had a chance to manipulate the block list.

You can also set $block->content here, which will override the content of the
block and prevent hook\_block\_view() from running.

