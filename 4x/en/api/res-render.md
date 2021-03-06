Renders a `view` and sends the rendered HTML string to the client.
Optional parameters:
- `locals`, an object whose properties define local variables for the view.
- `callback`, a callback function. If provided, the method returns both the
possible error and rendered string, but does not perform an automated response.
When an error occurs, the methohd invokes `next(err)` internally.

<div class="doc-box doc-notice">
The local variable `cache` enables view caching. Set it to `true`,
to cache the view during development; view caching is enabled in production by default.
</div>

```js
// send the rendered view to the client
res.render('index');

// if a callback is specified, the rendered HTML string has to be sent explicitly
res.render('index', function(err, html) {
  res.send(html);
});

// pass a local variable to the view
res.render('user', { name: 'Tobi' }, function(err, html) {
  // ...
});
```
