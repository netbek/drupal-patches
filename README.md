# drupal-patches

## Patches for core

## Patches for contrib

### CKEditor - Instance config

This patch allows one to override the global CKEditor config with per instance config. For example, if one has multiple editors on the same page and one sets `config.height = '600px';` at `/admin/config/content/ckeditor/edit/[profile]` then all editors have the same height. To set the height of a specific editor, e.g. summary, add the following to `hook_form_alter()`:

```php
$field_language = $form['body']['#language'];
$instance = 'edit-body-' . $field_language . '-0-summary';
drupal_add_js(array('ckeditor' => array('instanceConfig' => array($instance => array('height' => '200px')))), 'setting');
```

Version: 7.x-1.x commit [8499587](http://drupalcode.org/project/ckeditor.git/commit/8499587)

Patch: [ckeditor-instance-config.patch](https://raw.github.com/netbek/drupal-patches/7.x/contrib/ckeditor/ckeditor-instance-config.patch)
