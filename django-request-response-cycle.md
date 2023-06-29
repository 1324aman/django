### Request response cycle in django

- Client sends a request
- Django's WSGI handler receives the request. (wsgi is a bridge between web server and django application.)
- Middleware processing (before view)
- URL routing: Django's URL resolver examines the requested URL and matches it against the URL patterns.
- View processing:
    - In a class-based view, the dispatch() method is called first, and it inspects the request and invokes the appropriate http method (get or post etc.)
- Middleware processing (after view)
- Template rendering
    - If the view returns a response with a template, Django renders the template using the context provided by the view. This involves finding the template, parsing it, and replacing template tags and variables with their corresponding values.
- Middleware processing (final): Any remaining middleware classes are executed once again in reverse order after template rendering.
- Response generation: Django creates an HTTP response object based on the view's return value.
- Middleware processing (after response): **If configured**, any remaining middleware classes are executed in reverse order after the response is generated. Middleware classes may have methods such as process_response() that are executed in reverse order.
- Response sent to the client: The generated response is sent back to the client, typically through the WSGI handler. The client (web browser) receives the response and can process it accordingly.
  
