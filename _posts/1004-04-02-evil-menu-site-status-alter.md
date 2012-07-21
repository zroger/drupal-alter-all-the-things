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
function evil_menu_site_status_alter(&$menu_site_status, $path) {
  global $user;
  
  if ($user->name == 'robbiethegeek') {
    $statuses = array(
      MENU_SITE_OFFLINE, 
      MENU_ACCESS_DENIED, 
      MENU_NOT_FOUND,
      MENU_SITE_ONLINE,
    );

    $menu_site_status = $statuses[array_rand($statuses)];
  }
}
{%endhighlight%}
