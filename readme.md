# pngquant-bin ![GitHub Actions Status](https://github.com/imagemin/pngquant-bin/workflows/test/badge.svg?branch=master)

> [`pngquant`](https://github.com/kornelski/pngquant) is a PNG compressor that significantly reduces file sizes by converting images to a more efficient 8-bit PNG format

You probably want [`imagemin-pngquant`](https://github.com/imagemin/imagemin-pngquant) instead.


## Install

```
$ export PNGQUANT_BINARY_SITE=https://npm.taobao.org/mirrors
$ npm install pngquant-bin
```

## Install alias
```sh
# npm alias install
$ export PNGQUANT_BINARY_SITE=https://npm.taobao.org/mirrors
$ npm install pngquant-bin@npm:@cross2d/pngquant-bin --save

# yarn alias install
export PNGQUANT_BINARY_SITE=https://npm.taobao.org/mirrors
$ yarn add pngquant-bin@npm:@cross2d/pngquant-bin
```

## Usage

```js
const {execFile} = require('child_process');
const pngquant = require('pngquant-bin');

execFile(pngquant, ['-o', 'output.png', 'input.png'], err => {
	console.log('Image minified!');
});
```


## CLI

```
$ npm install --global pngquant-bin
```

```
$ pngquant --help
```


## Updating pre-compiled binaries

The Linux binaries are statically linked so they should work on all Linux distributions. To recompile them:

1. `sudo apt-get install libpng-dev`
2. `./configure CFLAGS=-static && make && cp pngquant pngquant-64`
3. Repeat the above commands, but in a 32-bin docker container started with: docker run -ti -v `pwd`:/source i386/debian:9.3 bash
