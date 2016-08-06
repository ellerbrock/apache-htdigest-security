![Apache Logo](https://github.frapsoft.com/top/apache.gif)

# htdigest authentication for Apache Webserver [![Build Status](https://travis-ci.org/ellerbrock/apache-htdigest-security.svg?branch=master)](https://travis-ci.org/ellerbrock/apache-htdigest-security) [![Open Source Love](https://badges.frapsoft.com/os/v1/open-source.svg?v=102)](https://github.com/ellerbrock/open-source-badge/) [![Gitter Chat](https://badges.gitter.im/frapsoft/frapsoft.svg)](https://gitter.im/frapsoft/frapsoft/)  

### Module `mod_auth_digest`

*Tutorial how to create [htdigest](http://httpd.apache.org/docs/current/mod/mod_auth_digest.html) authentication for Apache Webserver.*  

### 1.) create a [.htaccess](https://httpd.apache.org/docs/2.4/howto/htaccess.html) file  

***best practice: only serve secure data over a encrypted connection!***  

```
<Location "/var/www/website/wp-admin/">
    AuthType Digest
   	AuthName "protected"
    AuthDigestDomain "/wp-admin/" "https://myblog.loc/wp-admin/"
    AuthDigestProvider file
    AuthUserFile "/var/secure/.htpasswd"
    Require valid-user
</Location>
```


### 2.) create a `.htpasswd` file

`htdigest -c .htpasswd realm username`   

**important notice:** realm must be the same string you choose before for the "AuthName" setting.

***best practice: save the .htpasswd files outside of the public accessible webfolder.***  

### Contact / Social Media

*Get the latest News about Web Development, Open Source, Tooling, Server & Security*

[![Twitter](https://github.frapsoft.com/social/twitter.png)](https://twitter.com/frapsoft/)
[![Facebook](https://github.frapsoft.com/social/facebook.png)](https://www.facebook.com/frapsoft/)
[![Google+](https://github.frapsoft.com/social/google-plus.png)](https://plus.google.com/116540931335841862774)
[![Gitter](https://github.frapsoft.com/social/gitter.png)](https://gitter.im/frapsoft/frapsoft/)
[![Github](https://github.frapsoft.com/social/github.png)](https://github.com/ellerbrock/)

### Development by 

Developer / Author: [Maik Ellerbrock](https://github.com/ellerbrock/)  
Company: [Frapsoft](https://github.com/frapsoft/)


### License 

<a rel="license" href="http://creativecommons.org/licenses/by/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by/4.0/88x31.png" /></a><br />

This work by <a xmlns:cc="http://creativecommons.org/ns#" href="https://github.com/ellerbrock/" property="cc:attributionName" rel="cc:attributionURL">Maik Ellerbrock</a> is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by/4.0/">Creative Commons Attribution 4.0 International License</a>.