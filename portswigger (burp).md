# Portswigger practice

## 1. Path traversal
Basic exercise, basic idea – involved searching for a 'passwd' file by accessing directories/files that contain sensitive information.
+ Open test website in BurpSuite as target.
+ From the Proxy tab (HTTP History), send any image URL to the repeater.
+ Change (eg.) /image?filename=65.jpg –> /image?filename=../../../etc/passwd

Vuln successfully exploited, as code could be manipulated to lead to the 'etc' directory and to the targeted 'passwd' file.*

*ps: super easy to exploit since there's no security measures set in place to prevent unauth. access to files, such as an allowlist 
