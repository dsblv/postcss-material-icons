# postcss-material-icons [![Build Status](https://travis-ci.org/dsblv/postcss-material-icons.svg?branch=master)](https://travis-ci.org/dsblv/postcss-material-icons)

> PostCSS plugin that imports icons google's material design [icon library](https://design.google.com/icons/)


## Install

```
$ npm install --save postcss-material-icons
```


## Usage

```js
const material = require('postcss-material-icons');

const css = 'body {background: material(face, white, 18)}';

//Use stand-alone:
material.process(css).then(res => console.log(res.css));
//=> 'body {background: url(/* base64-encoded white face icon */)}'

// Or as PostCSS plugin:
postcss([material()]).process(css).then(res => console.log(res.css));
//=> 'body {background: url(/* base64-encoded white face icon */)}'
```

Icons are being [cached](https://github.com/floatdrop/cacha) in the file system, so you won't download them twice.


## CSS API

The plugin transforms `material()` into base64 encoded icon inside `url()` notation.

### material(icon, [color], [size])

#### icon

*Required*

Icon name in [the library](https://design.google.com/icons):

```css
.cart {
	background-image: material(shopping cart);
}
```

Yeah, without quotes and with whitespaces!

#### color

Default: `black`

Icon color. Either `black` or `white`.

#### size

Default: `24`

Icon size in pixels. `18`, `24`, `36` or `48`.


## License

MIT © [Dmitriy Sobolev](https://github.com/dsblv)
