This README provides guidance on configuring Apache server settings for optimal testing of the application using local host.

Please note that in a real application, the htpasswrd would not be located inside the htdocs of this directory, instead it would be located in the Apatche24 folder.
I have located this file in a folder called private within the htdocs file so the marker can compile and test that htaccess works without making any changes.
I have included a robots.txt that would help to prevent web crawlers from accessing or indexing the contents of the private folder.

In a real world application the private folder would be located in the Apatche24 folder and the htaccess file would read as below.

<Files "staffportal.html">
AuthName "Restricted Access"
AuthType Basic
AuthUserFile "C:/Apache24/private/.htpasswd"
Require valid-user
</Files>

* This application was tested on Apatche version 2.4 *
To make this application work on my device the port ID needed to be amended from port 80 to port 8080
To do this locate the httpd file in under C:\Apache24\conf
search 'listen 80' and amend this to 'Listen 8080'
To make htaccess work I also set the AllowOverride to All, this was done by searching the following location of the httpd file <Directory "${SRVROOT}/htdocs">
and scrolling down the the part that had 'AllowOverride none' and amedning it to 'AllowOverride All'