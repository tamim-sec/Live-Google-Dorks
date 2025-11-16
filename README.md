# Live-Google-Dorks

### Broad domain search w/ negative search

> site:example.com -www -shop -share -ir -mfa

### PHP extension w/ parameters

> site:example.com ext:php inurl:?
> site:example[.]com inurl:"scratch/category.php"
> site:example.com/webp


### Disclosed XSS and Open Redirects

> site:openbugbounty.org inurl:reports intext:"example.com"

### Juicy Extensions

> site:"example[.]com" ext:log | ext:txt | ext:conf | ext:cnf | ext:ini | ext:env | ext:sh | ext:bak | ext:backup | ext:swp | ext:old | ext:~ | ext:git | ext:svn | ext:htpasswd | ext:htaccess

### XSS prone parameters

> inurl:q= | inurl:s= | inurl:search= | inurl:query= | inurl:keyword= | inurl:lang= inurl:& site:example.com
> site:example.com "register forum"
> site:example[.]com inurl:id= | inurl:url= | inurl:redirect= | inurl:login | inurl:admin | inurl:page= | inurl:year= | inurl:view= | inurl:email= | inurl:type= | inurl:name= | inurl:p= | inurl:month= 

### Open Redirect prone parameters

> inurl:url= | inurl:return= | inurl:next= | inurl:redirect= | inurl:redir= | inurl:ret= | inurl:r2= | inurl:page= inurl:& inurl:http site:example.com

### SQLi Prone Parameters

> inurl:id= | inurl:pid= | inurl:category= | inurl:cat= | inurl:action= | inurl:sid= | inurl:dir= inurl:& site:example.com
> site:example.com ext:sql | ext:dbf | ext:mdb
> site:example.com intext:"sql syntax near" | intext:"syntax error has occurred" | intext:"incorrect syntax near" | intext:"unexpected end of SQL command" | intext:"Warning: mysql_connect()" | intext:"Warning: mysql_query()" | intext:"Warning: pg_connect()"
> site:example.com inurl:"php?sql=select" ext:php
> site:example.com "sql" "parent" intitle:index.of -injection

### SSRF Prone Parameters

> inurl:http | inurl:url= | inurl:path= | inurl:dest= | inurl:html= | inurl:data= | inurl:out= | inurl:callback  | inurl:domain=  | inurl:page= inurl:& site:example.com
> inurl:continue= | inurl:window= | inur:site= | inurl:return= | inurl:view= | inurl:port= | inurl:print= | inurl:export= | inurl:dir= site:example.com

### LFI Prone Parameters

> inurl:include | inurl:dir | inurl:detail= | inurl:file= | inurl:folder= | inurl:inc= | inurl:locate= | inurl:doc= | inurl:conf= inurl:& site:example.com

### RCE Prone Parameters

> inurl:cmd | inurl:exec= | inurl:query= | inurl:code= | inurl:do= | inurl:run= | inurl:read=  | inurl:ping= inurl:& site:example.com

### High % inurl keywords

> inurl:config | inurl:env | inurl:setting | inurl:backup | inurl:admin | inurl:php site:example[.]com
> inurl:conf | inurl:env | inurl:cgi | inurl:bin | inurl:etc | inurl:root | inurl:sql | inurl:backup | inurl:admin | inurl:php site:example[.]com
> site:example[.]com intitle:"index of"  inurl:/config/

### Sensitive Parameters/files

> inurl:email= | inurl:phone= | inurl:password= | inurl:secret= inurl:& site:example[.]com
> site:example.com filetype:pdf,xlsx,docx,csv
> site:example.com ext:doc | ext:docx | ext:odt | ext:pdf | ext:rtf | ext:sxw | ext:psw | ext:ppt | ext:pptx | ext:pps | ext:csv
> site:example.com inurl:readme | inurl:license | inurl:install | inurl:setup | inurl:config
> site:example.com ext:action | ext:struts | ext:do
> inurl:"/phpinfo.php" | inurl:".htaccess" | inurl:"/.git" example.com -github
> +inurl:example.com +ext:swf
> site:example.com intitle:"Index of" inurl:/backup/ "admin.zip"
> site:example.com intext:"index of" inurl:json-rpc
> site:example.com intext:"index of" inurl:jwks-rsa
> site:example.com intitle:"index of" "users.yml" | "admin.yml" | "config.yml"
> site:example.com intitle:"index of" "docker-compose.yml"
> site:example.com intext:"Index of" intext:"/etc"

### API Docs

> inurl:apidocs | inurl:api-docs | inurl:swagger | inurl:api-explorer site:"example[.]com"
> intitle:"index of" api_key | "api key" | apikey -pool site:"example[.]com"
> intitle:"index.of" intext:"api.txt" site:"example[.]com"

### Code Leaks

> site:pastebin.com "example.com"

> site:jsfiddle.net "example.com"

> site:codebeautify.org "example.com"

> site:codepen.io "example.com"

### Cloud Storage

> site:s3.amazonaws.com "example.com"

> site:blob.core.windows.net "example.com"

> site:googleapis.com "example.com"

> site:drive.google.com "example.com"

> site:dev.azure.com "example[.]com"

> site:onedrive.live.com "example[.]com"

> site:digitaloceanspaces.com "example[.]com"

> site:sharepoint.com "example[.]com"

> site:s3-external-1.amazonaws.com "example[.]com"

> site:s3.dualstack.us-east-1.amazonaws.com "example[.]com"

> site:dropbox.com/s "example[.]com"

> site:box.com/s "example[.]com"

> site:docs.google.com inurl:"/d/" "example[.]com"

### JFrog Artifactory

> site:jfrog.io "example[.]com"

### Firebase

> site:firebaseio.com "example[.]com"

### File upload endpoints

> site:example.com ”choose file”

## Dorks that work better w/o domain

### Apache Server Status Exposed

> site:*/server-status apache

### WordPress

> site:example[.]com inurl:/wp-admin/admin-ajax.php
> site:example[.]com inurl:/wp-json/wp/v2/users
> site:example.com inurl:wp- | inurl:wp-content | inurl:plugins | inurl:uploads | inurl:themes | inurl:download
> site:example.com inurl:*/wp-content/plugins/contact-form-7/
> site:example.com inurl:wp-content/uploads/wcpa_uploads
> site:example.com inurl:"wp-content" intitle:"index.of" intext:wp-config.php
> site:example.com inurl:"wp-content" intitle:"index.of" intext:backup"

### Drupal

> site:example.com inurl:user intitle:"Drupal" intext:"Log in" -"powered by"
> site:example.com inurl:user intitle:"Drupal" intext:"Log in" -"powered by"

### Joomla

> site:example.com inurl: /libraries/joomla/database/

### Sensitive field
> site:example[.]com "login" | inurl:login | allinurl:login portal | intitle:login | intitle:login portal | intext:login portal

### Sensitive information leakage
> site:example[.]com inurl:.gov password | credential | username filetype:log
> site:example[.]com inurl:nokia not for distribution | confidential | “employee only” | proprietary | top secret | classified | trade secret | internal | private filetype:pdf
> site:example[.]com inurl:.gov not for distribution | confidential | “employee only” | proprietary | top secret | classified | trade secret | internal | private | WS_FTP | ws_ftp | log | LOG filetype:log
> site:example[.]com inurl:.gov not for distribution | confidential | “employee only” | proprietary | top secret | classified | trade secret | internal | private filetype:xls
> site:example[.]com inurl:.gov not for distribution | confidential | “employee only” | proprietary | top secret | classified | trade secret | internal | private filetype:csv
> site:example[.]com inurl:.gov not for distribution | confidential | “employee only” | proprietary | top secret | classified | trade secret | internal | private filetype:doc
> site:example[.]com inurl:.gov not for distribution | confidential | “employee only” | proprietary | top secret | classified | trade secret | internal | private filetype:txt
> site:example[.]com inurl:.gov password | credential | username filetype:log
> intitle:"index of /" site:example[.]com
> site:example.com ext:bkf | ext:bkp | ext:bak | ext:old | ext:backup
> site:example.com intitle:"index of" github-api



### Blind Xss 

> site:example[.]com intitle:"contact.php" | intitle:"contactus" | intitle:"contactus.php" | intitle:"contactus.aspx" | intitle:"contactus.asp" | intitle:"contactus.html" | intitle:"contact-us.html" | intitle:"contact_us.html" | intitle:"contact.html" | intitle:"contactus.html"
> site:example[.]com inurl:"contact.php" | inurl:"contactus" | inurl:"contactus.php" | inurl:"contactus.aspx" | inurl:"contactus.asp" | inurl:"contactus.html" | inurl:"contact-us.html" | inurl:"contact_us.html" | inurl:"contact.html" | inurl:"contactus.html"
> site:example[.]com inurl:"feedback.php" | inurl:"send feedback" | inurl:"feedbackus.php" | inurl:"feedback.aspx" | inurl:"feedback.asp" | inurl:"feedback.html" | intitle:"send feedback"
> site:example[.]com inurl:"Send Us a Message" |intitle:"Send Us a Message"
> site:example[.]com intitle:"support.php" | intitle:"support" | intitle:"contactus.php" | intitle:"support.aspx" | intitle:"support.asp" | intitle:"support.html" | intitle:"support-us.html"
> site:example[.]com inurl:submit messages | inurl:submit  | inurl:submit messages | inurl:submit form | intitle:submit form
> site:example[.]com inurl:Support Center | intitle:Support Center
> site:example[.]com intitle:"submit.php" | intitle:"submit" | intitle:"submit.php" | intitle:"submit.aspx" | intitle:"submit.asp" | intitle:"submit.html" | intitle:"submit-us.html" | intitle:"submit_us.html" | intitle:"submit.html" | intitle:"submit.html"
> site:example[.]com inurl:submit a request | intitle:submit a request
> site:example[.]com inurl:submit a report | intitle:submit a report
> site:example[.]com intext:Attachments (optional)
> site:example[.]com intext:Please choose a request type below
