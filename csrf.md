#### CSRF stands for Cross-Site Request Forgery
For e.g, if a user is logged into a site and its info is in browser.
Another malicious site which contains some link or button, 
it uses the logged in user info from session stored in browser cookies, to perform some actions on the original site.
The malicious site may contain form, or executes some js on page load of malicious site, and that js performs some action on orginal site.
For e.g, one action could be, changing users password using current logged in info.

#### check [here](https://docs.djangoproject.com/en/4.2/ref/csrf/#how-it-works) how csrf protection works in django 

When a form is rendered on template a csrf token is sent from backend, which is a stored in a hidden input field and it is included in template using tag {% csrf_token %}.
When form is submitted, it is again checked in backend and verified.
CsrfViewMiddleware generates and sends token with the response. Every time it generates a new token whenever it is called (means page is reloaded).

#### A csrf token cannot be accessed by other sites due to the [same origin policy](https://developer.mozilla.org/en-US/docs/Web/Security/Same-origin_policy)
