## Child elements
```html
<div class="group bg-blue-500 hover:bg-purple-500">
	<div class="bg-black group-hover:bg-red-500"></div>
</div>
```
## Sibling elements
```html
<div class="peer bg-blue-500 hover:bg-purple-500">
<div class="bg-green-500 peer-hover:bg-orange-500">
```
## Named groups/peers
```html
<div class="peer/name group/other bg-blue-500 hover:bg-purple-500">
	<div class="bg-black group-hover/other:bg-red-500"></div>
</div>
<div class="bg-green-500 peer-hover/name:bg-orange-500">
```