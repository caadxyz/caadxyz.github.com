---
layout: post
title:  "How to add a logo to the WordPress Customizer"
permalink: blog/howto-add-logo-customizer
categories:
  - WordPress
  - Customizer
---

Depending on your use-case, you may want to add a logo on the top pf the customizer, replacing the "preview" notice. Unfortunately there is no filter available yet to do that, but you can still do it using some simple jQuery.

This is a simple function you can use to do just that:

### Using the WordPress API:

```php
<?php

/**
 * This is a simple function that replaces the preview notice with an image.
 * This example uses an image from http://domain.com/image.png so please add your own.
 */
function custom_add_logo_to_customizer() { ?>
	<script>
	jQuery(document).ready(function($) {
		"use strict";
		$('div#customize-info .preview-notice').replaceWith(
            '<img src="http://domain.com/image.png">'
        );
	});
	</script>
	<?php
}
add_action( 'customize_controls_print_scripts', 'custom_add_logo_to_customizer' );

?>
```

### Using Kirki

Alternatively, if you're using the [Kirki Toolkit](http://kirki.org) plugin you can do it by simply adding your logo URL on the plugin's configuration. For more info please check out the plugin's [Wiki page](https://github.com/reduxframework/kirki/wiki/Styling-the-Customizer).
