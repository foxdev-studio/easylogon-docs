# Plugin API reference
Last update: 13-Dec-21 ([View change history](https://github.com/foxdev-studio/easylogon-docs/commits/master/2-API%20Reference/1-Plugin.md))

## Table of Contents
- [Plugin attributes](#plugin-attributes)
	- [Structure sample](#structure-sample)
- [Plugin CSS selectors](#plugin-css-selectors)
	- [#ezl-btn](##ezl-btn)
	- [.ezl-container](#.ezl-container)
- [Flyout customization](#flyout-customization)
- [Related links](#related-links)

## Plugin attributes
### Structure sample
```html
<!-- Should be placed at the place of plugin render -->
<div
	class="ezl-container"
	data-widgetType="inlineButton"
	data-login="input[name=email]"
	data-password="input[name=password]"
	data-submit="input[name=submit]">
</div>

<!-- Should be placed at the bottom of the <body> -->
<script src="https://easylogon.foxdev.studio/ezlog.js" defer></script>
```

| Attribute | Description | Valid values |
| --------- | ----------- | ------------ |
| data-widgettype | Type of widget appearance. Go to [widget creation panel](/profile#CreateWidget) to see difference in action | `inlineButton`, `button`, `inline`, `link` |
| data-login | CSS selector which points at an `<input />` field for user's email/login on authentication page | Valid CSS selector pointing at the exact `<input />` element |
| data-password | CSS selector which points at an `<input />` field for user's password on authentication page | Valid CSS selector pointing at the exact `<input />` element |
| data-login | CSS selector which points at an HTML element which is used as "Sign in" button on authentication page | Valid CSS selector pointing at the exact `<input />` element |

## Plugin CSS selectors
### #ezl-btn
This CSS selector points at the "Sign in with QR code" button (or link) an allow you to customize its appearance

#### Supported widget types
- `inlineButton`
- `button`
- `link`

#### Examples
```css
#ezl-btn
{
	background: gray;
	border: 2px solid red;
	color: white;
	font-family: monospace;
}
```
![Customized button](https://easylogon.foxdev.studio/docs/custom-btn.png)

### .ezl-container
This CSS selector points at the plugin container

> **Note**
> Even though `.ezl-container` is presented in all widget types. It is advised to use this selector only with `inline` widget

#### Supported widget types
- `inline`

#### Examples
```css
.ezl-container
{
	background: gray;

	/* Inline widget requires size at least 200x100 pixels */
	width: 200px;
	height: 200px;
}

.ezl-container iframe
{
	filter: brightness(0) invert(1);
}
```
![Customized inline widget](https://easylogon.foxdev.studio/docs/custom-inline.png)

> **Note**
> Since widget's QR code is currently displayed inside an `iframe`, it is impossible for now to customize it more precisely

## Flyout customization
Currently we support only button (and partially `inline`) customization. At the moment customization of a flyout is unsupported

## Related links
- [Plugin integration](/docs/1-Get%20started/3-Plugin%20integration)
- [Plugin customization](/docs/1-Get%20started/4-Plugin%20customization)