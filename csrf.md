#### CSRF stands for Cross-Site Request Forgery
For e.g, if a user is logged into a site and its info is in browser.
Another malicious site which contains some link or button, 
it uses the logged in user info from browser to perform some actions on the original site.
The malicious site may contain form, or executes some js on page load of malicious site.
For e.g, one actions could be, changing users password using current logged in info.

#### check [here](https://docs.djangoproject.com/en/4.2/ref/csrf/#how-it-works) how csrf protection works in django 
