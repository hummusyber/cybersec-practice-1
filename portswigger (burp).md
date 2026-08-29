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

Lab 1 (Unprotected admin functionality):
+ Append 'robots.txt' to site URL. (file specifying which files can/cannot be accessed by web robots/auto. engine crawlers)
+ Notice disallowed items. (administrator-panel)
+ Go to disallowed URL.
+ Delete user 'carlos'.
Vuln exploited by taking advantage of no actual check of admin details–access is open to anyone who has knowledge of URL.Thus, information can be easily tampered with.
