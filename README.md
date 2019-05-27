# Reject-IE-6-9

Usage
1) Upload files on yoursite in directory "reject_ie", or any else
2) Add into ".htaccess" after "RewriteEngine on" (this way for Apache server only)

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
RewriteCond %{REQUEST_FILENAME} !-f
RewriteCond %{HTTP_USER_AGENT} "MSIE [6-9]" [NC]
RewriteRule ^(.*)$ /reject_ie/index.html [R=301,L]
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

3) if it doesn't work (it usually happens when the server is not running Apache), add to index.php at the beginning

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
if (preg_match( "/.*MSIE [6-9].*/", $_SERVER['HTTP_USER_AGENT'])) {
    header('Location: /reject_ie/index.html');
};
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
