MediaWiki OAuth Library
=======================

This library provides a simple means to performing an OAuth handshake with a MediaWiki installation using (see https://www.mediawiki.org/wiki/Extension:OAuth).  

Usage
-----

```python
import mwoauth
oauth = mwoauth.OAuth(
    "https://en.wikipedia.org/w/index.php", 
    "<client key>", 
    "<client secret>"
)
redirect, resource_owner = oauth.initiate()
print("Go to: %s" % redirect)

auth = oauth.complete(resource_owner, raw_input("response_qs: "))

print oauth.identify(auth)
```
