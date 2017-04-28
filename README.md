# Reject-IE-6-8

Usage
1) Upload files on yoursite in directory "reject_ie", or any else
2) Add into ".htaccess" after "RewriteEngine on" 

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
RewriteCond %{REQUEST_FILENAME} !-f
RewriteCond %{HTTP_USER_AGENT} "MSIE [6-8]" [NC]
RewriteRule ^(.*)$ /reject_ie/index.html [R=301,L]
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
