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
function user_menu_site_status_alter(&$menu_site_status, $path) {
  if ($menu_site_status == MENU_SITE_OFFLINE) {
    // If the site is offline, log out unprivileged users.
    if (user_is_logged_in() && !user_access('access site in maintenance mode')) {
      module_load_include('pages.inc', 'user', 'user');
      user_logout();
    }

    if (user_is_anonymous()) {
      switch ($path) {
        case 'user':
          // Forward anonymous user to login page.
          drupal_goto('user/login');
        case 'user/login':
        case 'user/password':
          // Disable offline mode.
          $menu_site_status = MENU_SITE_ONLINE;
          break;
  // ...
{%endhighlight%}
