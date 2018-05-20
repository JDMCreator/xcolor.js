# xcolor.js

`xcolor.js` is a JavaScript implementation of LaTeX package `xcolor`. It is a very complex package, so it only supports some features.

### Supported features

* Models supported : `rgb`, `RGB`, `cmy`, `cmyk`, `HTML`, `gray`, `Gray`, `hsb`, `Hsb`, `HSB` and `wave`.
* Named colors (default colors, colors from DVIPS, colors from SVG and colors from X11)
* Blended colors (e.g. `yellow!20` or `yellow!40!black!30!red`)
* Inverted colors (e.g. `-yellow` or `-yellow!20`)

### Documentation

#### window.xcolor()

Syntax : `Array window.xcolor(String color, Optional String model, Optional Boolean dvips)`

Returns an `Array` that represents the RGB value of the color where all numbers are part of `[0,255]`.

* **`color`** : String. The definition of the color.
* **`model`** (Optional) : String. The model of the color (e.g. `rgb`, `RGB`, `cmyk`, `HTML`). Leaving this argument empty means that your color is a named color.
* **`dvips`** (Optional) : Boolean. If `true`, `dvips` name colors have a higher priority than `SVG` colors. Default : `false`.

Example :

```js
window.xcolor("-yellow!20");
window.xcolor("0,255,255", "rgb");
window.xcolor("Green", "rgb", true);
```

#### window.xcolor.register()

Syntax : `Array window.xcolor.register(String name, Number red, Number green, Number blue)`

Alternative syntax : `Array window.xcolor.register(String name, Array RGB)`

Register a named color.

#### window.xcolor.remove()

Syntax : `Boolean window.xcolor.remove(String name)`

Remove the named color. Returns `true` is the color named `name` existed and `false` otherwise.

#### window.xcolor.erase()

Syntax : `Boolean window.xcolor.erase(String name)`

Remove all named colors.

### License

Licensed under MIT.