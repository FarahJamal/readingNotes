# WRRC 



    1- A user opens his browser, types in a URL, and presses Enter.
    2- When a user presses Enter, the browser makes a request for that URL.
    3- The request hits the Rails router (config/routes.rb). The router maps the URL to the correct controller and action to handle the request.
    4- The action receives the request and passes it on to the view.
    5- The view renders the page as HTML.
    6- The controller sends the HTML back to the browser. The page loads and the user sees it.

***In this way, the request/response cycle is a useful way to see what a Rails app’s files and folders are for and how they fit together.***

![](https://content.codecademy.com/projects/3/request-response-cycle-static.svg)