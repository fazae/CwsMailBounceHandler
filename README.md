# CwsMailBounceHandler

CwsMailBounceHandler is a PHP class to help webmasters handle bounce-back, feedback loop and ARF mails in standard DSN (Delivery Status Notification, RFC-1894).
It checks your IMAP inbox or eml files and delete or move all bounced emails.
If a bounce is malformed, it tries to extract some useful information to parse status.

## Installation

### classical way

* Enable the [php_imap](http://php.net/manual/en/book.imap.php) extension if you want to use the IMAP open mode.
* Download [CwsDump](https://github.com/crazy-max/CwsDump) and [CwsDebug](https://github.com/crazy-max/CwsDebug).
* Copy the ``class.cws.mbh.php`` file and ``Cws`` folder in a folder on your server.
* try it with ``php example.php``

### with composer

* Enable the [php_imap](http://php.net/manual/en/book.imap.php) extension if you want to use the IMAP open mode.
* Install with composer
```
composer require crazy-max/cws-mail-bounce-handler:dev-master
```
* and try it :
```
cd vendor/crazy-max/cws-mail-bounce-handler
php example.composer.php
```


## Getting started

See ``example.php`` file sample to help you.<br />
You can use eml files in the emls folder for testing.

## Post-process

A result object (Cws\MailBounceHandler\Models\Result) is available to process custom post-actions :

![](https://raw.github.com/crazy-max/CwsMailBounceHandler/master/example.png)

## Methods

**openImapLocal** - Open a IMAP mail box in local file system.<br />
**openImapRemote** - Open a remote IMAP mail box.<br />
**openEmlFolder** - Open a folder containing eml files on your system.<br /><br />

**processMails** - Process the messages in a mailbox or a folder.<br /><br />

**getStatusCodeExplanations** -Get explanations from DSN status code via the RFC 1893.<br /><br />

**isMailboxOpenMode** - Check if open mode is mailbox.<br />
**isFileOpenMode** - Check if open mode is file.<br />
**isNeutralProcessMode** - Check if process mode is neutral mode.<br />
**isMoveProcessMode** - Check if process mode is move mode.<br />
**isDeleteProcessMode** - Check if process mode is delete mode.<br />
**getProcessMode** - The method to process bounces.<br />
**setNeutralProcessMode** - Set the method to process bounces to neutral. (default)<br />
**setMoveProcessMode** - Set the method to process bounces to move.<br />
**setDeleteProcessMode** - Set the method to process bounces to delete.<br />
**setProcessMode** - Set the method to process bounces.<br />
**getMailboxService** - Mailbox service.<br />
**setImapMailboxService** - Set the mailbox service to IMAP. (default)<br />
**setMailboxService** - Set the mailbox service.<br />
**getMailboxHost** - Mailbox host server.<br />
**setMailboxHost** - Set the mailbox host server. (default localhost)<br />
**getMailboxUsername** - The username of mailbox.<br />
**setMailboxUsername** - Set the username of mailbox.<br />
**setMailboxPassword** - Set the password needed to access mailbox.<br />
**getMailboxPort** - The mailbox server port number.<br />
**setImapMailboxPort** - Set the mailbox server port number to IMAP (143). (default)<br />
**setTlsSslMailboxPort** - Set the mailbox server port number to TLS/SSL (995).<br />
**setMailboxPort** - Set the mailbox server port number.<br />
**getMailboxSecurity** - The mailbox security option.<br />
**setMailboxSecurity** - Set the mailbox security option. (default const MAILBOX_SECURITY_NOTLS)<br />
**getMailboxCert** - Certificate validation.<br />
**setMailboxCertValidate** - Set the certificate validation to VALIDATE.<br />
**setMailboxCertNoValidate** - Set the certificate validation to NOVALIDATE. (default)<br />
**setMailboxCert** - Set the certificate validation.<br />
**getMailboxName** - Mailbox name.<br />
**setMailboxName** - Set the mailbox name, other choices are (Tasks, Spam, Replies, etc...). (default INBOX)<br />
**getMailboxHandler** - The resource handler for the opened mailbox (POP3/IMAP/NNTP/etc...).<br />
**getMaxMessages** - Maximum limit messages processed in one batch.<br />
**setMaxMessages** - Set the maximum limit messages processed in one batch (0 for unlimited).<br />
**isPurge** - Check if purge unknown messages.<br />
**setPurge** - Set the mailbox server port number.<br />
**getError** - The last error message.<br />

## License

LGPL. See ``LICENSE`` for more details.

## More infos

http://www.crazyws.fr/dev/classes-php/classe-de-gestion-des-bounces-en-php-C72TG.html
