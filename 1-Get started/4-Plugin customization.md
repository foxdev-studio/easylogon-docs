# Plugin customization
Last update: 13-Dec-21 ([View change history](https://github.com/foxdev-studio/easylogon-docs/commits/master/1-Get%20started/3-Plugin%20customization.md))

## Table of Contents
- [Plugin types](#obtain-code)
- [Custom CSS](#custom-css)
- [Related links](#related-links)

When everything is up and running, it's time to think about appearance. We provide some tools to customize widget

## Plugin types
There're four basic types of widget which work out of box:
- Inline (`inline`) - QR code is placed next to sign in form
- Button (`button`) - "Sign in with QR code" button which is placed under sign in button
- Inline button (`inlineButton`) - Small "Sign in with QR code" button which is placed on the right from password field
- Link (`link`) - Hyperlink which opens QR code in another browser tab

![Widget types](https://easylogon.foxdev.studio/docs/widget-types.png)

To see how each type of widget acts, go to [widget contructor panel](https://easylogon.foxdev.studio/profile#CreateWidget)

## Custom CSS
Since QR code button is injected into your website code, it can be heavily customized with CSS

You can attach new CSS file to your page head and use `#ezl-btn` selector to apply styling rules to the widget

### Example
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

For more information about customization and limitations, see [Plugin API reference](/docs/2-API%20Reference/1-Plugin)

## Related links
- [Plugin API reference](/docs/2-API%20Reference/1-Plugin)