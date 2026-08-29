# Portswigger practice

## 1. Path traversal
Basic exercise, basic idea – involved searching for a 'passwd' file by accessing directories/files that contain sensitive information.
+ Open test website in BurpSuite as target.
+ From the Proxy tab (HTTP History), send any image URL to the repeater.
+ Change (eg.) /image?filename=65.jpg –> /image?filename=../../../etc/passwd
Vuln successfully exploited, as code could be manipulated to access the 'etc' directory and the targeted 'passwd' file.*

_*ps: super easy to exploit since there are no security measures set in place to prevent unauthorized access. access to files, such as an allowlist_

## 2. Access control
Involves three main factors:
+ Authentication: Confirms that the user is who they claim to be.
+ Sesh mgmt.: Identifying what HTTPS requests are being made.
+ Access control: Whether the user has permission to perform the attempted action.

### LAB 1 (Unprotected admin functionality):
+ Appended 'robots.txt' to site URL. (file specifying which files can/cannot be accessed by web robots/auto. engine crawlers)
+ Noticed disallowed items. (administrator-panel)
+ Went to disallowed URL.
+ Deleted user 'carlos'.
Vuln exploited by taking advantage of no actual check of admin details–access is open to anyone who has knowledge of URL. Thus, information can be easily tampered with.

### LAB 2 ('' w/ an unpredictable URL):
*similar to previous lab, but admin panel is located at a more unpredictable location.
+ There is no robots.txt file available upon checking, so I checked the page source.
+ Noticed an 'if' block of code and found the admin panel.
+ Appended admin panel to the website URL.
+ Deleted user 'carlos'.
Vuln exploited since the URL to the admin panel was available in the source code (on the client side itself). So it was easily accessible simply by checking the page source.

