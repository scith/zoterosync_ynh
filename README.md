ZoteroSync for YunoHost (phpZoteroWebDAV)
----------------------------------------

Warning: This YunoHost app is still in development. Use it at your own risk!

**WARNING**: File sync does not work at the moment with a private install (only library sync works in private)

At the moment, one app = one Zotero library. If you want to manage several libraries, you will need to install one app per user, enter their respective API and userID keys, and give them rights to their own app. I know it is not ideal but it is the way phpZoteroWebDAV works at the moment.

Features
--------

- Sync library attachment to any webhosting space that supports PHP (including freely available ones).
This means your attachment data is never stored on computers (clients or servers) that you do not control yourself.
- Access your Zotero library on your own webspace through the zotero.org server API, including sorting, detail view, custom number of items per page etc
- Browse your Zotero collections from any web browser
- View your synced attachments (incl. web snapshots) from any web browser without having to use zotero.org's storage server
- Enjoy complete security with support for HTTPS connections

A live demo is available at: http://blog.holz.ca/phpZoteroWebDAV-demo/

TO BE DONE
----------
- Check if BACKUP and RESTORE scripts are working
- Find a better way to manage multiple users instead of multi-instance?
- Improve user interface

Installation and Configuration Instructions
-------------------------------------------
First, you need to retrieve your Zotero API key and userID for API calls.
Login to http://www.zotero.org, navigate to Settings > Feeds/API and create a new API key. Give it a name and leave the other parameters unchanged. Once created, you will see the API key and userID in the Settings > Feeds/API menu.

Once installed, ZoteroSync is almost ready to be used. You just have to configure your Zotero client.

1. If you have a self-signed SSL certificate, you will first need to make Zotero recognize your certificate: https://www.zotero.org/support/kb/cert_override
In your Firefox profile directory ("%appdata%\Mozilla\Firefox\Profiles\"), copy the file "cert_override.txt".
Paste it in your Zotero profile directory (see https://www.zotero.org/support/kb/cert_override)

2. In your zotero client (i.e. in firefox or standalone zotero), open the sync tab in the preferences.  In the “File Syncing” section, select “WebDAV” from the list. In the URL field, enter your YunoHost path (e.g. www.example.com/zotero) and then add “/webdav_server.php”, so that the whole path (including the “/zotero” suffix that cannot be changed) would be www.example.com/zotero/webdav_server.php/zotero
Enter your username and password and click "Verify Server" to verify that everything is working properly.

3. You are ready to go!

For more information about the setup: http://blog.holz.ca/2011/11/phpzoterowebdav-installation/

License
-------

phpZoteroWebDAV was originally written by Christian Holz and is licensed under the AGPLv3 license.
Significant updates have been made by:
* fishburn (Real name unknown - https://github.com/fishburn)
* David Dean

phpZoteroWebDAV includes the following third party components:
- The WebDAV server PEAR module written by Hartmut Holzgraefe as well as the PEAR base module, both licensed under the PHP license (http://www.php.net/license/3_01.txt)
- The libZotero class for zotero API connection, released under an unknown open source license (https://github.com/fcheslack/libZotero)
- The zotero.org css style sheet, apparently released under the AGPLv3 license (http://www.gnu.org/licenses/agpl.html))

ZoteroSync for YunoHost forks https://github.com/ddean4040/phpZoteroWebDAV
