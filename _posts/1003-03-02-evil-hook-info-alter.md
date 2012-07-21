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
function evil_hook_info_alter(&$info) {
  $hooks['token_info']['group']       = 'no-tokens-for-you';
  $hooks['token_info_alter']['group'] = 'no-tokens-for-you';
  $hooks['tokens']['group']           = 'no-tokens-for-you';
  $hooks['tokens_alter']['group']     = 'no-tokens-for-you';
}
{%endhighlight%}
