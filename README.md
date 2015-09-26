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


### Picture - Issue [2443295](https://www.drupal.org/node/2443295#comment-9671233)

This patch deletes `picture_polyfill_version` on uninstall.

Version: 7.x-2.x commit [741f444](http://drupalcode.org/project/picture.git/commit/741f444)

Patch: [picture-delete-variable-picture-polyfill-version-2443295-1.patch](https://raw.github.com/netbek/drupal-patches/7.x/contrib/picture/picture-delete-variable-picture-polyfill-version-2443295-1.patch)


### Picture - Issue [2443319](https://www.drupal.org/node/2443319#comment-9671327)

This patch deletes formatter settings on uninstall.

Version: 7.x-2.x commit [741f444](http://drupalcode.org/project/picture.git/commit/741f444)

Patch: [picture-delete-formatter-settings-on-uninstall-2443319-1_0.patch](https://raw.github.com/netbek/drupal-patches/7.x/contrib/picture/picture-delete-formatter-settings-on-uninstall-2443319-1_0.patch)


### Picture - Issue [2574163](https://www.drupal.org/node/2574163#comment-10377421)

This patch removes newline characters from theme_picture() output.

Version: 7.x-2.12

Patch: [picture-remove-newline-2574163-2.patch](https://raw.github.com/netbek/drupal-patches/7.x/contrib/picture/picture-remove-newline-2574163-2.patch)


### WYSIWYG Filter - Issue [2575617](https://www.drupal.org/node/2575617#comment-10379437)

This patch adds support for media attribute, with validation.

Version: 7.x-2.12

Patch: [wysiwyg_filter-support_media_attribute_validation-2575617-1.patch](https://raw.github.com/netbek/drupal-patches/7.x/contrib/wysiwyg_filter/wysiwyg_filter-support_media_attribute_validation-2575617-1.patch)


### WYSIWYG Filter - Issue [2575617](https://www.drupal.org/node/2575617#comment-10379437)

This patch adds support for media attribute, without validation.

Version: 7.x-2.12

Patch: [wysiwyg_filter-support_media_attribute-2575617-1.patch](https://raw.github.com/netbek/drupal-patches/7.x/contrib/wysiwyg_filter/wysiwyg_filter-support_media_attribute-2575617-1.patch)
