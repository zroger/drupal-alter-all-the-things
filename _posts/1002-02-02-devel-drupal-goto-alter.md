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
function devel_drupal_goto_alter($path, $options, $http_response_code) {
  global $user;

  if (isset($path) && !devel_silent()) {
    if (isset($user) && function_exists('user_access') 
                     && user_access('access devel information') 
                     && variable_get('devel_redirect_page', 0)) {
      $destination = function_exists('url') ? url($path, $options) : $path;
      $output = t_safe('<p>The user is being redirected to 
                        <a href="@destination">@destination</a>.</p>', 
                        array('@destination' => $destination));
      drupal_deliver_page($output);

      // Don't allow the automatic redirect to happen.
      exit();
    }
    // ...
  }
}
{%endhighlight%}
