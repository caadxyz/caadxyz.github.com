---
layout: post
title:  "How to remove the themes changer from the WordPress Customizer"
permalink: blog/howto-remove-themes-changer-wp-customizer
categories:
  - WordPress
  - Customizer
---

The WordPress Customizer is not just for themes, it can also be used for plugins. I've seen for example a brilliant newsletters plugin that used the customizer for composing the actual emails, and the implementation was awesome. In cases like that, you may want to remove the WordPress Themes switcher from the WordPress Customizer.

This is a simple function you can use to do just that:

```php
<?php

/**
 * This function removes the themes section from the customizer.
 */
function custom_remove_themes_section() {
	global $wp_customize;
	$wp_customize->remove_section( 'themes' );
	$wp_customize->remove_control( 'active_theme' );
}
add_action( 'customize_register', 'custom_remove_themes_section' );

?>
```
