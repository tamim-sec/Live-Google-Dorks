# Live-Google-Dorks

### Broad domain search w/ negative search

> site:example.com -www -shop -share -ir -mfa

### PHP extension w/ parameters

> site:example.com ext:php inurl:?
> site:example.com inurl:"scratch/category.php"
> site:example.com/webap


### Disclosed XSS and Open Redirects

> site:openbugbounty.org inurl:reports intext:"example.com"

### Juicy Extensions

> site:"example[.]com" ext:log | ext:txt | ext:conf | ext:cnf | ext:ini | ext:env | ext:sh | ext:bak | ext:backup | ext:swp | ext:old | ext:~ | ext:git | ext:svn | ext:htpasswd | ext:htaccess

### XSS prone parameters

> inurl:q= | inurl:s= | inurl:search= | inurl:query= | inurl:keyword= | inurl:lang= inurl:& site:example.com
> site:target.com "register forum"
> site:example.com inurl:id= | inurl:url= | inurl:redirect= | inurl:login | inurl:admin | inurl:page= | inurl:year= | inurl:view= | inurl:email= | inurl:type= | inurl:name= | inurl:p= | inurl:month= 

### Open Redirect prone parameters

> inurl:url= | inurl:return= | inurl:next= | inurl:redirect= | inurl:redir= | inurl:ret= | inurl:r2= | inurl:page= inurl:& inurl:http site:example.com

### SQLi Prone Parameters

> inurl:id= | inurl:pid= | inurl:category= | inurl:cat= | inurl:action= | inurl:sid= | inurl:dir= inurl:& site:example.com

### SSRF Prone Parameters

> inurl:http | inurl:url= | inurl:path= | inurl:dest= | inurl:html= | inurl:data= | inurl:domain=  | inurl:page= inurl:& site:example.com

### LFI Prone Parameters

> inurl:include | inurl:dir | inurl:detail= | inurl:file= | inurl:folder= | inurl:inc= | inurl:locate= | inurl:doc= | inurl:conf= inurl:& site:example.com

### RCE Prone Parameters

> inurl:cmd | inurl:exec= | inurl:query= | inurl:code= | inurl:do= | inurl:run= | inurl:read=  | inurl:ping= inurl:& site:example.com

### High % inurl keywords

> inurl:config | inurl:env | inurl:setting | inurl:backup | inurl:admin | inurl:php site:example[.]com
> site:example[.]com intitle:"index of"  inurl:/config/

### Sensitive Parameters/files

> inurl:email= | inurl:phone= | inurl:password= | inurl:secret= inurl:& site:example[.]com
> site:example[.]com filetype:pdf,xlsx,docx,csv

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

### Drupal

> intext:"Powered by" & intext:Drupal & inurl:user

### Joomla

> site:*/joomla/login

### Sensitive field
> site:target.com "login" | inurl:login | allinurl:login portal | intitle:login | intitle:login portal | intext:login portal

### Sensitive information leakage
> site:example.com inurl:.gov password | credential | username filetype:log
> site:example.com inurl:nokia not for distribution | confidential | “employee only” | proprietary | top secret | classified | trade secret | internal | private filetype:pdf
> site:example.com inurl:.gov not for distribution | confidential | “employee only” | proprietary | top secret | classified | trade secret | internal | private | WS_FTP | ws_ftp | log | LOG filetype:log
> site:example.com inurl:.gov not for distribution | confidential | “employee only” | proprietary | top secret | classified | trade secret | internal | private filetype:xls
> site:example.com inurl:.gov not for distribution | confidential | “employee only” | proprietary | top secret | classified | trade secret | internal | private filetype:csv
> site:example.com inurl:.gov not for distribution | confidential | “employee only” | proprietary | top secret | classified | trade secret | internal | private filetype:doc
> site:example.com inurl:.gov not for distribution | confidential | “employee only” | proprietary | top secret | classified | trade secret | internal | private filetype:txt
> site:example.com inurl:.gov password | credential | username filetype:log
