`Use`-Registry
===

What is `use`?
---

It's a library to make it easier to work with other libraries in the browser. So you can go like:
```javascript
<use>bootstrap</use>
```
instead of
```javascript
<link rel="stylesheet" href="//netdna.bootstrapcdn.com/bootstrap/3.1.1/css/bootstrap.min.css">
<script src="//netdna.bootstrapcdn.com/bootstrap/3.1.1/js/bootstrap.min.js"></script>
```
It starts on page load and does not require to be  installed or something like that.
(That comes with the tradeoff of slightly longer loading times, of course)

Setup
---

Just put `<script use src="//is.gd/useJS"></script>` on your html. Done!

Usage
---

###Declarative/HTML API
In the `script[use]`-Tag place the libraries that you want to have imported. The script will do the rest for you!

E.g. if you wanted to import `angular` it would look like:

```html
<use>angular</use>
```

adding `bootstrap` wounld require:

```html
<use>angular bootstrap</use>
```
There is another way:
```html
<script use src="//is.gd/usejs">angular bootstrap</script>
```
this leaves out the need of to separate elements in your html or want to have standard compliant html.

###Javascript API
If you feel the need to import libraries in javascript, there is a javascript function, that you can call.
```javascript
use('angular bootstrap')
```

> **NOTE:** `use` automatically recognises if a library is requested multiple times and will ignore the unnecessary ones.
 
Supported Libraries
---

All currently supported libraries can be found in the [`libs`](https://github.com/csicar/Registry/tree/master/libs)folder.

###Add Libraries
To make really `use` really easy to use, it needs to support as many libraries as possible. To add a library, just put a file named `[library name].js` in the [`libs`](https://github.com/csicar/Registry/tree/master/libs)folder. If there is a CDN that provides the library you can use this to pull it:
```javascript
use.get([CDN-URL]);
```
or:
```
yepnope([CDN-URL]);
```

`use` internally uses yepnope, so you can just use the [yepnope api](http://yepnopejs.com/#api).

If the library you want to add requires a library that is already in the registry, you can just use `use`.
E.g. for `foundation`:
```javascript
yepnope(['foundation/foundation.css']);
use('modernizr jquery', function(){
	console.log(jQuery)
	yepnope('fundation/foundation.js')
});
```