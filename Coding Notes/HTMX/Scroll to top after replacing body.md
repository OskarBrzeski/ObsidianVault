The htmx property `hx-swap` can take the value of `show:window:top` which forces the page to move to the top of the page after the body element is replaced.
```html
<a hx-get="/" hx-target="body" hx-swap="show:window:top">Home</a>
```