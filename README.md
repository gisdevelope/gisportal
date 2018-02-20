Web portal for QGIS projects published by EQWC
==============================================

This is start page - Web portal for browsing and opening QGIS projects published with [**Extended QGIS Web Client.**](https://github.com/uprel/gisapp)

User registration and login is now part of this. Next steps are planned to have complete web administration part for publishing projects and layers, delegating user permissions...

Built with Codeigniter and Bootstrap.

## Demo
Visit **<a target="_blank" href="http://test.level2.si">Demo by Level2</a>**

## Setup

> You go through this after you setup gisapp!

> This code relies on database from gisapp. Make sure you are running latest [database version](https://github.com/uprel/gisapp/wiki/3.-Managing-Database#upgrading)!

1. Checkout into web root to have gisportal folder beside gisapp folder (EQWC)
1. Setup database connection in application/config/database.php
1. Setup base_site, default language and other EQWC settings at bottom of application/config/config.php
1. Edit header_logo.png in assets/img folder.
1. Enable integration with gisportal in gisapp/client_common/settings.js
1. To preserve session information from gisapp to gisportal you have to edit php.ini and change line

    ```
    session.name = PHPSESSID
    to
    session.name = sess_
    ```

    This means that you login to gisportal and then browse all public projects or projects you have permission without
    new login.

## Email service
If you entered correct gmail info at the bottom of config.php you enabled email service using Google SMTP server. That means you don't need to setup own mail server. This service can be used to sending emails from gisapp or gisportal.

[Test mail - localhost example](http://localhost/gisportal/index.php/mail/test)

Email service is currently used with new User Feedback control in gisapp and with Editor plugin.
It is planned to be used with gisportal (for sending emails to users) and for other tasks in gisapp.

If you have problems sending email check this settings for your Google account: [Google-account-configuration](../../wiki/Google-account-configuration)

## Shortening URL
Now your gisportal URL looks like this:

```http://localhost/gisportal/index.php/login```

Read [Shortening URL on Wiki](https://github.com/uprel/gisportal/wiki/Shortening-URL) to remove "/gisportal/index.php", like this:

```http://localhost/login```

> You can test this on provided Demo link above!


## Thumbnail images

gisportal uses thumbnail images for client and project display. Images should be in 3:2 proportions, for example 300 px width X 200 px height. Copy images to assets/img/clients and assets/img/projects folder with client or project name as it is in database in PNG format.

## Translations

1. Check if your language exists in [system folder](https://github.com/uprel/gisportal/tree/master/system/language). 
1. If not get it from [Codeigniter Translations](https://github.com/bcit-ci/codeigniter3-translations)
1. Create folder with language name in [application/language](https://github.com/uprel/gisportal/tree/master/application/language) folder.
1. Copy gisportal_lang.php from any other languages to new language folder and translate contents.
1. Add new language in config/config.php at the bottom: $config['available_languages']. Here you can also remove unwanted languages.
1. If you wish you can change default language in application/config/config.php.

## Contributing

Support this project by [**DONATING**](http://level2.si/product/donation-extended-qgis-web-client/).

You are also welcome to contribute to the project by testing, requesting new features, translating, submitting code, ...
Read this [tutorial about making changes to repositories](https://help.github.com/articles/fork-a-repo/).

Thank you!

## Support

Contact us for:
* support
* custom development

Uroš Preložnik, http://level2.si
