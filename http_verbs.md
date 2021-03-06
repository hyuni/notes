# HTTP VERBS

from [here](http://www.restapitutorial.com/lessons/httpmethods.html)
and [here](http://flask.pocoo.org/docs/0.12/quickstart/)

## POST
The browser tells the server that it wants to post some new information to that URL and that the server must ensure the data is stored and only stored once. This is how HTML forms usually transmit data to the server.

canonical thing to do is return a `201` with the ID of the created object post `POST`

## GET
The browser tells the server to just get the information stored on that page and send it. This is probably the most common method.

GET	Obtain information about a resource	http://example.com/api/orders/123 (retrieve order #123)
GET	Obtain information about a resource	http://example.com/api/orders (retrieve order list)

## PUT
Similar to POST but the server might trigger the store procedure multiple times by overwriting the old values more than once. Now you might be asking why this is useful, but there are some good reasons to do it this way. Consider that the connection is lost during transmission: in this situation a system between the browser and the server might receive the request safely a second time without breaking things. With POST that would not be possible because it must only be triggered once.

## PATCH
update, modify

## DELETE
Remove the information at the given location.

## HEAD
The browser tells the server to get the information, but it is only interested in the headers, not the content of the page. An application is supposed to handle that as if a GET request was received but to not deliver the actual content.

## OPTIONS
Provides a quick way for a client to figure out which methods are supported


---



POST	Create a new resource	http://example.com/api/orders (create a new order, from data provided with the request)

PUT	Update a resource	http://example.com/api/orders/123 (update order #123, from data provided with the request)

DELETE	Delete a resource	http://example.com/api/orders/123 (delete order #123)
