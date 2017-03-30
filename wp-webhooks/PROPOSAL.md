# WordPress + Web Hooks =  🎉
## What do we need?

- A WordPress Plugin with an Admin Panel so the WP Admin can match WordPress Hooks (like `post_updated`) to Web Hooks.
  - I suggest using [Vue](https://vuejs.org/v2/guide/) for the front-end as there was a discussion on `#engineering` about using it on a real project to be able to compare the DX with React.

- Some PHP Classes to handle the actual event mapping. Including a Wrapper clas for dispatching events, we can add events to a Queue like SQS or RabbitMQ or we can do an HTTP Request with Guzzle. Think of [HTTPlug](https://github.com/php-http/httplug) but for dispatching our RestHooks WS Events. 
 
  **NOTE**: Event management should be done thru the RESTful API *but* event dispatching can be done in the way I just described.
 
 - A Backend for the actual RESTful Hooks Web Services. I'm specifically thinking about using [Kraken](https://github.com/kraken-php/framework) or [amp](https://github.com/amphp). These match more closely an event-driven mindest than using Laravel or Phalcon. And they say it is [more performant too](http://kraken-php.com/#sec-performance). We can also easily make a NodeJS implementation just to contrast ;)
