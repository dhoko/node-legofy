# node-legofy

*This project is a Node.js port of the [Legofy](https://github.com/JuanPotato/Legofy) Python library from [Juan Potato](https://github.com/JuanPotato). Full feature and API parity is not ensured.*

LEGOfy aims at converting an image (no GIF support) into a mosaic of 1&times;1 colored bricks. It is useless but hell a lot of fun. See the [example](#example) for, y’know, an example.

## Usage (CLI)

```sh
bin/legofy < images/sample.png > images/sample.lego.png
```

## Usage (Node)

```js
import legofy from 'node-legofy'

inputStream
  .pipe(legofy())
  .pipe(outputStream)
```

## Usage (Vinyl/Gulp)

Using the [vinyl-transform] package to adapt a Node.js transform stream
to a Vinyl stream.

[vinyl-transform]: https://www.npmjs.com/package/vinyl-transform

```js
import fs from 'vinyl-fs'
import transform from 'vinyl-transform'
import legofy from 'node-legofy'

fs.src('images/*.png')
  .pipe(transform(legofy))
  .pipe(fs.dest('dest/'))
```

## Example

![Initial image](https://raw.githubusercontent.com/HugoGiraudel/node-legofy/master/images/sample.png)

![Processed image](https://raw.githubusercontent.com/HugoGiraudel/node-legofy/master/images/sample.lego.png)

## Credits

* [Juan Potato](https://github.com/JuanPotato) for the original Python library
* [Hugo Giraudel](https://twitter.com/HugoGiraudel) for the Node.js version
* [Valérian Galliat](https://twitter.com/valeriangalliat) for the Node.js refactoring and help
