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
function field_system_info_alter(&$info, $file, $type) {
  if ($type == 'module' && module_hook($file->name, 'field_info')) {
    $fields = field_read_fields(array('module' => $file->name),
      array('include_deleted' => TRUE));
    if ($fields) {
      $info['required'] = TRUE;

      if (module_exists('field_ui')) {
        $explanation = t('Field type(s) in use - see !link', 
          array('!link' => l(t('Field list'), 'admin/reports/fields')));
      }
      else {
        $explanation = t('Fields type(s) in use');
      }

      $info['explanation'] = $explanation;
    }
  }
}
{%endhighlight%}
