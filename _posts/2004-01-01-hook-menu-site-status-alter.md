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

<h1><code>hook_menu_site_status_alter()</code></h1>

Control site status before menu dispatching.

The hook is called after checking whether the site is offline but before the
current router item is retrieved and executed by menu\_execute\_active\_handler().
If the site is in offline mode, $menu\_site\_status is set to MENU\_SITE\_OFFLINE.
