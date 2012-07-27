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

<h1><code>hook_menu_breadcrumb_alter()</code></h1>

Alter links in the active trail before it is rendered as the breadcrumb.

This hook is invoked by menu\_get\_active\_breadcrumb() and allows alteration
of the breadcrumb links for the current page, which may be preferred instead of
setting a custom breadcrumb via drupal\_set\_breadcrumb().

