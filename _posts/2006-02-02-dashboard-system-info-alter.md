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
function dashboard_system_info_alter(&$info, $file, $type) {
  if ($type == 'theme') {
    // Add the dashboard regions (the "inactive" region should always appear
    // last in the list, for usability reasons).
    $dashboard_regions = dashboard_region_descriptions();
    if (isset($dashboard_regions['dashboard_inactive'])) {
      $inactive_region = $dashboard_regions['dashboard_inactive'];
      unset($dashboard_regions['dashboard_inactive']);
      $dashboard_regions['dashboard_inactive'] = $inactive_region;
    }
    $info['regions'] += $dashboard_regions;
    $info['overlay_regions'] = !empty($info['overlay_regions']) 
      ? array_merge($info['overlay_regions'], dashboard_regions()) 
      : dashboard_regions();
  }
}
{%endhighlight%}
