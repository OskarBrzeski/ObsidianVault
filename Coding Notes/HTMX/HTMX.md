```html
<element hx-verb="/endpoint" hx-option="example"></element>
```

Send HTTP request to server
```html
<element hx-get="/endpoint"></element>
<element hx-post="/endpoint"></element>
<element hx-put="/endpoint"></element>
<element hx-patch="/endpoint"></element>
<element hx-delete="/endpoint"></element>
```

Set how request is triggered
```html
<element hx-trigger="mouseenter"></element>
<element hx-trigger="mouseleave"></element>
<element hx-trigger="change"></element>
<element hx-trigger="click"></element>
```

Modify trigger properties
```html
<element hx-trigger="mouseenter once"></element>
<element hx-trigger="mouseenter delay:5s"></element>
<element hx-trigger="mouseenter from:#elementid"></element>
```

Show progress indicator while waiting for response
```html
<div hx-get="/data">
    <element class="htmx-indicator"></element>
</div>

<div hx-get="/data" hx-indicator="#my-indicator"></div>
<element class="htmx-indicator" id="my-indicator"></element>
```

Target element to swap HTML into
```html
<div id="target"></div>
<element hx-get="/endpoint" hx-target="#target"></element>
```

Change how content is swapped in HTML
```html
<element hx-get="/endpoint" hx-swap="innerHTML"></element>
<element hx-get="/endpoint" hx-swap="outerHTML"></element>

<element hx-get="/endpoint" hx-swap="beforebegin"></element>
<element hx-get="/endpoint" hx-swap="afterbegin"></element>
<element hx-get="/endpoint" hx-swap="beforeend"></element>
<element hx-get="/endpoint" hx-swap="afterend"></element>
```

Swap content into different elements
```html
<element hx-get="/endpoint"></element>
<div id="first"></div>
<div id="second"></div>

Inside Response:
<element id="first" hx-swap-oob="true"></element>
<element id="second" hx-swap-oob="true"></element>
```

Send form data in HTML request
```html
<form>
    <input type="text" name="example"/>
    <button hx-post="/endpoint" hx-target="#replace-target"/>
</form>
```

Send other data in HTML request
```html
<input type="text" name="example" id="source"/>

<button hx-post="/endpoint" hx-include="#source"></button>
```
