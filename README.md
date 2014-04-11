`Use`-Registry
===

Installation
---

Just put `<script use src="//csicar.kd.io/p.js"></script>` on your html. Done!

Usage
---

###Declarative  Api
In the `script[use]`-Tag place the libraries that you want to have imported. The script will do the rest for you!

E.g. if you wanted to import `angular` it would look like:

```html
<script use src="//csicar.kd.io/p.js">angular</script>
```

adding `bootstrap` wounld require:

```html
<script use src="//csicar.kd.io/p.js">angular bootstrap</script>
```

###Imperial Api
```javascript
use('angular bootstrap')
```

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