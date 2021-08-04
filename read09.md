What does REST stand for?
REST is an architectural style for building distributed systems based on hypermedia. REST is independent of any underlying protocol and is not necessarily tied to HTTP. However, most common REST API implementations use HTTP as the application protocol,and this guide focuses on designing REST APIs for HTTP.

REST APIs are designed around a __.
REST APIs are designed around Resources.

What is an identifer of a resource? Give an example.
which are any kind of object, data, or service that can be accessed by the client.A resource has an identifier, which is a URI that uniquely identifies that resource. For example, the URI for a particular customer order might be: HTTP

What are the most common HTTP verbs?
The primary or most-commonly-used HTTP verbs (or methods, as they are properly called) : are

POST.
GET.
PUT.
PATCH.
DELETE.
What should the URIs be based on?
Is a unique sequence of characters that identifies a logical or physical resource used by web technologies. URIs may be used to identify anything, including real-world objects, such as people and places, concepts, or information resources such as web pages and books.Each time you modify the web API or change the schema of resources, you add a version number to the URI for each resource. The previously existing URIs should continue to operate as before, returning resources that conform to their original schema.

Give an example of a good URI.
/customers is the path to the customers collection, and /customers/5 is the path to the customer with ID equal to 5.

What does it mean to have a ‘chatty’ web API? Is this a good or a bad thing?
Another factor is that all web requests impose a load on the web server. The more requests, the bigger the load web APIs that expose a large number of small resources. Such an API may require a client application to send multiple requests to find all of the data that it requires. Instead, you might want to denormalize the data and combine related information into bigger resources that can be retrieved with a single request. However, you need to balance this approach against the overhead of fetching data that the client doesn’t need. ((Bad))

What status code does a successful GET request return?
A successful GET method typically returns HTTP status code 200 (OK).

What status code does an unsuccessful GET request return?
If the resource cannot be found, the method should return 404 (Not Found).

What status code does a successful POST request return?
The HTTP response indicates whether the order was placed successfully or not. When possible, resource URIs should be based on nouns (the resource) and not verbs (the operations on the resource).

What status code does a successful DELETE request return?
If the delete operation is successful, the web server should respond with HTTP status code 204 (No Content), indicating that the process has been successfully handled, but that the response body contains no further information.