SilverStripe 3 Custom HTMLEditorField
===================================

Overview
--------------

This module adds two features to HTMLEditorField in SilverStripe 3:

1. it allows you to set a custom body class on each editor field (for styling the content differently)
2. it allows you to assign different HTMLEditorConfigs to each HTMLEditorField (eg to have different toolbars)




Maintainer Contacts
-------------------
*  Nathan Cox (<nathan@flyingmonkey.co.nz>)


Requirements
------------
* SilverStripe 3.0+


Installation Instructions
-------------------------

1. Place the files in a directory called customhtmleditorfield in the root of your SilverStripe installation
2. Visit yoursite.com/dev/build to rebuild the database


Documentation
-------------
[GitHub Wiki](https://github.com/nathancox/silverstripe-customhtmleditorfield/wiki)


Example code:
```php
<?php

// make a new TinyMCE config called "footer" by copying the default ("cms") config
$footerConfig = CustomHtmlEditorConfig::copy('footer', 'cms');
// remove the third row of the editor toolbar: no tables in the footer!
$footerConfig->setButtonsForLine(3, array());

// make an HtmlEditorField
$fields->addFieldToTab('Root.Footer', $footerField = new HtmlEditorField('FooterText', 'Footer'));

// assign the "footer" TinyMCE config to this field
$footerField->setEditorConfig('footer');

// set the editor's body class.  This will make it class="typography footer-content"
$footerField->setBodyClass('footer-content');
```



Known Issues
------------
[Issue Tracker](https://github.com/nathancox/silverstripe-customhtmleditorfield/issues)
