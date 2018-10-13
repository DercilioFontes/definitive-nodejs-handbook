# [The definitive Node.js handbook](https://medium.freecodecamp.org/the-definitive-node-js-handbook-6912378afc6e)

## A web server

```
const http = require('http');

const hostname = '127.0.0.1';
const port = 3000;

const server = http.createServer((req, res) => {
    res.statusCode = 200;
    res.setHeader('Content-Type', 'text/plain');
    res.end('Hello World\n');
});

server.listen(port, hostname, () => {
    console.log(`Server running at http://${hostname}:${port}/`);
});
```

## [A TUTORIAL TO JAVASCRIPT ARROW FUNCTIONS](https://flaviocopes.com/javascript-arrow-functions/)

Arrow functions are not suited as object methods.

Arrow functions cannot be used as constructors as well, when instantiating an object will raise a TypeError.

This is where regular functions should be used instead, when dynamic context is not needed.

This is also a problem when handling events. DOM Event listeners set this to be the target element, and if you rely on this in an event handler, a regular function is necessary:

```
const link = document.querySelector('#link')
link.addEventListener('click', () => {
  // this === window
})
```

```
const link = document.querySelector('#link')
link.addEventListener('click', function() {
  // this === link
})
```