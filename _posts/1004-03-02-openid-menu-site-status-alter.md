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
function openid_menu_site_status_alter(&$menu_site_status, $path) {
  // Allow access to openid/authenticate even if site is in offline mode.
  if ($menu_site_status == MENU_SITE_OFFLINE && user_is_anonymous() 
      && $path == 'openid/authenticate') {
    $menu_site_status = MENU_SITE_ONLINE;
  }
}
{%endhighlight%}

