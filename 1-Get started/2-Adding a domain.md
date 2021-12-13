# Adding a domain
Last update: 18-Nov-21 ([View change history](https://github.com/foxdev-studio/easylogon-docs/commits/master/1-Get%20started/2-Adding%20a%20domain.md))

## Table of Contents
- [Add new domain](#add-new-domain)
- [Verify domain](#verify-domain)
	- [Option 1: DNS verification](#option-1-dns-verification)
	- [Option 2: File verification](#option-2-file-verification)
- [Next steps](#next-steps)

## Add new domain
### On registration page
[As soon as you created your account](https://easylogon.foxdev.studio/get-started), you can add your domains. Simply type in your domain into the text field and click "Next"
![Add domain on account creation](https://easylogon.foxdev.studio/docs/add-domain-getstarted.png)

> **Note**
> Don't include protocol or path when adding a domain:
> **Incorrect:**
> ```
> https://example.com
> https://en.example.com/index.html
> ```
> **Correct:**
> ```
> example.com
> en.example.com
> ```

If you want to use EasyLogon on all your subdomains, prepend an asterisk wildcard to your domain name:
```
*.example.com
```
This will include all subdomains you have on your primary domain. For example:
- en.example.com
- ru.example.com
- forum.example.com
- app.example.com
- etc.

If you have more than one domain, you'd like to connect, enumerate them, separating with semicolon sign (;)

For example, if you type in following string:
```
*.example.com;myweb.site;site.test.com
```
You will add following domains to your account:
- example.com (with all subdomains)
- myweb.site
- site.test.com

### On profile page
If you don't want to add domains now, you can do it later on your [profile page](https://easylogon.foxdev.studio/profile)

Go to Domains section and click "+ Add new domain"

![Add domain on profile page](https://easylogon.foxdev.studio/docs/add-domain-profile1.png)

Type in your domain and press Enter or "+" button

![Add domain on profile page](https://easylogon.foxdev.studio/docs/add-domain-profile2.png)

Just like on the Get Started page, you can use wildcards to include all subdomains

## Verify domain
Once you've added your domain to the account, you need to verify it before you can use QR sign in on your website.

To do so, go to your [profile page](https://easylogon.foxdev.studio/profile) and in Domains section click on your domain that requires verification

![Verify domain](https://easylogon.foxdev.studio/docs/verify-domain.png)

From now, you have two options to verify your domain: with DNS record or with file

### Option 1: DNS verification
To verify your domain with DNS you will need to add a new DNS record on your domain registrar website

Here some instructions on how to add DNS records for most popular providers:
- [GoDaddy](https://www.godaddy.com/help/add-an-a-record-19238)
- [NameCheap](https://www.namecheap.com/support/knowledgebase/article.aspx/10357/2254/video-how-do-i-add-a-txt-record-for-my-domain/)
- [Name.com](https://www.name.com/support/articles/115004972547-Adding-a-TXT-Record)

If you use another provider do the following steps:
1. [Identify you domain host](https://support.google.com/a/answer/48323)
2. In a second browser window or tab, sign in to your domain host account
3. Go to your domain’s DNS records. The page might be called something like DNS Management, Name Server Management, Control Panel, or Advanced Settings
4. Select the option to add a new record

DNS record details are shown in the domain verification window:

![DNS Verification](https://easylogon.foxdev.studio/docs/verify-dns.png)

This is how it looks when you add DNS record on Name.com:

![Adding DNS record on Name.com](https://easylogon.foxdev.studio/docs/verify-dns1.png)

Click "Add record", go back to EasyLogon tab and click "Check verification" to verify your domain

> **Note**
> It may take up to 48 hours for DNS servers to sync your changes, so if verification fails, try to check verification later

If verification is successfull, the page will reload and "requires verification" label will disappear

> **Note**
> After successful verification you should not delete the DNS entry, because our service will periodically re-verify your domain to ensure that it is still yours

### Option 2: File verification
Alternatively, you can verify your domain by uploading a text file to the root of your website

First, download file from domain verification window by clicking "Download file"

![Download file](https://easylogon.foxdev.studio/docs/verify-file1.png)

Then upload the file to the root folder of your website on your server. Here some ways to do so:

If you have a dedicated VPS/VDS server, see [Transfer Files Between Remote and Local Systems Over SSH](https://linuxhandbook.com/transfer-files-ssh/)

If you use a hosting for your website, see instructions for control panel, installed on your hosting:
- [Plesk](https://docs.plesk.com/en-US/12.5/customer-guide/websites-and-domains/website-content/uploading-content-with-file-manager.74105/#:~:text=%20To%20upload%20a%20website%20from%20your%20computer,Upload%20Files%2C%20select%20the%20archive%20file%2C...%20More%20)
- [cPanel](https://www.peopleshost.com/2018/07/how-to-upload-files-using-file-manager-in-cpanel/)

As the result, the file should be accessible via browser at `https://yourdomain.com/_ezlverification_challenge.txt`

If you done it right, when navigating to `https://yourdomain.com/_ezlverification_challenge.txt` you should see your verification string

When it's done, click "Check verification" on EasyLogon domain verification window

If verification is successfull, the page will reload and "requires verification" label will disappear

> **Note**
> After successful verification you should not delete the file, because our service will periodically re-verify your domain to ensure that it is still yours

## Next steps
- [Plugin integration](/docs/1-Get%20started/3-Plugin%20integration)
- [Plugin customization](/docs/1-Get%20started/4-Plugin%20customization)