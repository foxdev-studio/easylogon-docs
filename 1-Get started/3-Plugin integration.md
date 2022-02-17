# Plugin integration
Last update: 23-Dec-21 ([View change history](https://github.com/foxdev-studio/easylogon-docs/commits/master/1-Get%20started/3-Plugin%20integration.md))

## Table of Contents
- [Obtain code](#obtain-code)
	- [CSS selectors](#css-selectors)
- [Insert code to your website](#insert-code-to-your-website)
	- [React](#react)
- [Next steps](#next-steps)

Once you created account, added and verified your domain, it's time to add QR code widget to your website

## Obtain code
Go to your [profile page](https://easylogon.foxdev.studio/profile#CreateWidget) and click "Get widget code" button in Domains section

On Configure widget panel you can see how widget will look on your website in an interactive preview section

You can change widget appearance by changing widget type

![Widget configuration](https://easylogon.foxdev.studio/docs/widget-preview.png)

### CSS selectors
Next step is to bind your login/password fields so widget can automatically insert user's credentials and "click" sign in button

Watch this video to know how to obtain selectors:

<iframe width="560" height="315" src="https://www.youtube.com/embed/ozwB8-TVusA?cc_load_policy=1" title="Obtaining CSS selectors for EasyLogon plugin integration // @FoxDev Studio" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

Materials:
- [Copy CSS Selector extension for Chrome](https://chrome.google.com/webstore/detail/copy-css-selector)
- [Validation script](https://easylogon.foxdev.studio/docs/test-script.js)

## Insert code to your website
When all fields are filled and tested, next step is to insert generated code into your sign in page

Click "Copy" button at the bottom of panel

![Copy widget code](https://easylogon.foxdev.studio/docs/widget-copy.png)

Open HTML code of your authentication page. If you use a CMS on your website, learn how to edit page source code

<!--Here some tutorial videos on popular CMS:
- [WordPress]()
- [Wix]()
- [Squarespace]()
- [Joomla]()
- [Drupal]()
- [DataLife Engine]()-->

Insert container part of the plugin into place you'd like to see the widget and the script part at the bottom of the `<body>` tag

![Paste code into webpage](https://easylogon.foxdev.studio/docs/paste-code.png)

> **Note**
>
> If you have problems with plugin integration, feel free to [contact our support](https://easylogon.foxdev.studio/support) and we'll do our best to assist you or even setup integration for you. This is free

### React
If your web application is using ReactJS framework, you need to perform additional steps:

Instead of pasting script block of plugin (second part of code on picures above), paste following code into `componentDidMount` method of your component (if you are using class-based components):
```js
componentDidMount()
{
	var script = document.createElement("script");
	script.src = "https://easylogon.foxdev.studio/ezlog.js";
	script.defer = true;
	script.async = true;
	document.body.appendChild(script);
}
```

or if you're using functional components in `useEffect` method:

```js
useEffect(() =>
{
	var script = document.createElement("script");
	script.src = "https://easylogon.foxdev.studio/ezlog.js";
	script.defer = true;
	script.async = true;
	document.body.appendChild(script);
}, [ ]);
```

## Next steps
- [Plugin customization](/docs/1-Get%20started/4-Plugin%20customization)
