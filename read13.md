## HTTP Status Codes
[really funny website to learn about codes](https://http.cat/)

In your own words, describe what each group of status code represents:

- `100` - 199Permalink These are informational status codes; they usually tell the client that the header part of the request has been received and the server will try to comply with a transmission demand of the client.

- `200` - 299Permalink These are the success codes.

- `300` - 399Permalink These are redirection codes. They tell the client that the resource they are requesting isn’t available at the expected location anymore.


- `400` - 499Permalink These are the client error codes. They are all about invalid requests a client sent to a server. There are several causes to this, timeouts, wrong URI, missing authentication, etc.

- `500` - 599Permalink These are the server error codes. Often they indicate problems with overwhelmed servers or unreachable servers behind proxies, but sometimes they can be directly related to client requests that trigger error exceptions on the server.
What is a status code 202?
 The 202 response is intentionally non-committal.

`UPDATE`
An update can be implemented with an HTTP PUT or PATCH method. The difference lies in the amount of data the client has to send to the backend.

`PUT`
requires the client to send an entire representation of a resource to update it.

`PATCH`
requires the client only send parts of the representation of the resource to update it.

`DELETE`
The delete action can be implemented with the HTTP DELETE method.

- 414 Request-URI Too Long -
This is sometimes the case when the endpoint is right, and the resource exists, but the query makes the URL too long to be interpreted.

 - The HTTP 403 Forbidden client error status response code indicates that the server understood the request but refuses to authorize it.

##### Middleware :
is software that provides common services and capabilities to applications outside of what's offered by the operating system.

What does app.use(express.json()) do?
express. json() is a method inbuilt in express to recognize the incoming Request Object as a JSON Object. This method is called as a middleware .

***What is the difference beween PUT and PATCH?***

 The main difference between the` PUT` and `PATCH` method is that the `PUT` method uses the request URI to supply a modified version of the requested resource which replaces the original version of the resource, whereas the` PATCH` method supplies a set of instructions to modify the resource.

- 500 Internal Server Error
The HyperText Transfer Protocol (HTTP) 500 Internal Server Error server error response code indicates that the server encountered an unexpected condition that prevented it from fulfilling the request.

***What is the difference between a status 200 and a status 201?***
 The 200 status code is by far the most common returned. It means, simply, that the request was received and understood and is being processed. A 201 status code indicates that a request was successful and as a result, a resource has been created (for example a new page).


 ![](https://2.bp.blogspot.com/-si7_P93nugw/V2EWBbdQzWI/AAAAAAAAAms/_cH4EWW9ZmUgQF6H6j4SZ26lJGGJ9TTkQCLcB/s1600/Screenshot_21.jpg)