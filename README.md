# ✉️ awsm-mailer
AWSM package for sending emails.

### Features

* 30 Pre-configured services (Gmail, Hotmail, SendGrid...etc)
* HTML content as well as plain text alternative
* 32 HTML template engines (handlebars, jade, haml...etc)
* Easy HTML styling with Juice
* Embedded images in HTML
* Email Attachments
* Unicode to use any characters
In your JAWS project root directory, run:

### Quick Usage
In your JAWS project root directory, run:

```
jaws module install https://github.com/jaws-framework/jaws-core-js
jaws module install https://github.com/eahefnawy/awsm-mailer
```

Set the following env vars (using CLI or the .env file):

```
EMAIL_SERVICE=Gmail
EMAIL_SERVICE_USER=username@gmail.com
EMAIL_SERVICE_PASS=password
```

deploy your code with `JAWS dash`, then test the Lambda with the following event:

```
{
  "from": "username@gmail.com",
  "to": "receiver@address.com",
  "subject": "Hello",
  "template": "welcome",
  "context": {
    "first_name": "Sam",
    "last_name": "Smith"
  }
}

```

This will use the `welcome` template coupled with the context/data (first_name & last_name).
You should receive an email that says:

```
Welcome Sam Smith

```

You can edit the template text by editing these two files:

```
<project-dir>/back/aws_modules/awsm-mailer/send/templates/html.handlebars
<project-dir>/back/aws_modules/awsm-mailer/send/templates/text.handlebars
```

### Supported Services
This package supports the following 30 service, pre-configured and ready to use. You just provide the username/password:

* **'1und1'**
* **'AOL'**
* **'DebugMail.io'**
* **'DynectEmail'**
* **'FastMail'**
* **'GandiMail'**
* **'Gmail'**
* **'Godaddy'**
* **'GodaddyAsia'**
* **'GodaddyEurope'**
* **'hot.ee'**
* **'Hotmail'**
* **'iCloud'**
* **'mail.ee'**
* **'Mail.ru'**
* **'Mailgun'**
* **'Mailjet'**
* **'Mandrill'**
* **'Naver'**
* **'Postmark'**
* **'QQ'**
* **'QQex'**
* **'SendCloud'**
* **'SendGrid'**
* **'SES'**
* **'Sparkpost'**
* **'Yahoo'**
* **'Yandex'**
* **'Zoho'**

### Template Engines
awsm-mailer comes with a `welcome` template for demonstration. You can add/remove templates from the following directory:

```
<project-dir>/back/aws_modules/awsm-mailer/send/templates/
```

awsm-mailer uses handlebars as the default template engine. You can use any other template engine by adding it to the `package.json` file and update dependencies with `npm install`.

Here's the full list of supported templates:

- [atpl](https://github.com/soywiz/atpl.js)
- [doT.js](https://github.com/olado/doT) [(website)](http://olado.github.io/doT/)
- [dust (unmaintained)](https://github.com/akdubya/dustjs) [(website)](http://akdubya.github.com/dustjs/)
- [dustjs-linkedin (maintained fork of dust)](https://github.com/linkedin/dustjs) [(website)](http://linkedin.github.io/dustjs/)
- [eco](https://github.com/sstephenson/eco)
- [ect](https://github.com/baryshev/ect) [(website)](http://ectjs.com/)
- [ejs](https://github.com/visionmedia/ejs)
- [haml](https://github.com/visionmedia/haml.js) [(website)](http://haml-lang.com/)
- [haml-coffee](https://github.com/9elements/haml-coffee) [(website)](http://haml-lang.com/)
- [hamlet](https://github.com/gregwebs/hamlet.js)
- [handlebars](https://github.com/wycats/handlebars.js/) [(website)](http://handlebarsjs.com/)
- [hogan](https://github.com/twitter/hogan.js) [(website)](http://twitter.github.com/hogan.js/)
- [htmling](https://github.com/codemix/htmling)
- [jade](https://github.com/visionmedia/jade) [(website)](http://jade-lang.com/)
- [jazz](https://github.com/shinetech/jazz)
- [jqtpl](https://github.com/kof/node-jqtpl) [(website)](http://api.jquery.com/category/plugins/templates/)
- [JUST](https://github.com/baryshev/just)
- [liquor](https://github.com/chjj/liquor)
- [lodash](https://github.com/bestiejs/lodash) [(website)](http://lodash.com/)
- [mote](https://github.com/satchmorun/mote) [(website)](http://satchmorun.github.io/mote/)
- [mustache](https://github.com/janl/mustache.js)
- [nunjucks](https://github.com/mozilla/nunjucks) [(website)](https://mozilla.github.io/nunjucks)
- [QEJS](https://github.com/jepso/QEJS)
- [ractive](https://github.com/Rich-Harris/Ractive)
- [react](https://github.com/facebook/react)
- [swig](https://github.com/paularmstrong/swig) [(website)](http://paularmstrong.github.com/swig/)
- [templayed](http://archan937.github.com/templayed.js/)
- [liquid](https://github.com/leizongmin/tinyliquid) [(website)](http://liquidmarkup.org/)
- [toffee](https://github.com/malgorithms/toffee)
- [underscore](https://github.com/documentcloud/underscore) [(website)](http://documentcloud.github.com/underscore/)
- [walrus](https://github.com/jeremyruppel/walrus) [(website)](http://documentup.com/jeremyruppel/walrus/)
- [whiskers](https://github.com/gsf/whiskers.js)

after chosing your template engine, make sure the file extentions of the template files match the template you chose. For examples:

```
html.{{ext}}
text.{{ext}}
style.{{ext}}
```