## Top navbar
```html
<a  hx-get="/"
    hx-target="body"
    hx-push-url="true"
>Home</a>

<a  hx-get="/services"
    hx-target="body"
    hx-push-url="true"
>Services</a>

<a  hx-get="/contactus"
    hx-target="body"
    hx-push-url="true"
>Contact Us</a>
```

The HTML returned from these GET request should contain the entire document. HTMX automatically decides to only replace the `body` element.