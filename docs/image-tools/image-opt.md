# Image Optimisation
Start by reading this excellent [essential image optimisation](https://images.guide) ebook by Addy Osmani. The image optimisation tools used in the codekit are configured to implement his recommendations and are loosely based on the great [ImageOptim](https://imageoptim.com) app for Mac.

Image optimisation / minification is performed using the node imagemin package. This node package provides a pluggable api where a range of common compression tools can be used to optimise images in a lossless manor. <https://freshman.tech/image-optimisation/> documents an example of how to configure the imagemin node package and settings for each of the compression plugins can be found on their npm package page (linked in the table below). Images can be passed through multiple filters to try and obtain the optimal compression.

| Plugin | Use |
| --- | --- |
| [imagemin-gifsicle](https://www.npmjs.com/package/imagemin-gifsicle) | GIF optimisation |
| [imagemin-jpegoptim](https://www.npmjs.com/package/imagemin-jpegoptim) | Jpeg optimisation |
| [imagemin-jpegtran](https://www.npmjs.com/package/imagemin-jpegtran) | Jpeg optimisation |
| [imagemin-optipng](https://www.npmjs.com/package/imagemin-optipng) | png optimisation |
| [imagemin-pngcrush](https://www.npmjs.com/package/imagemin-pngcrush) | png optimisation |
| [imagemin-pngout](https://www.npmjs.com/package/imagemin-pngout) | png optimisation |
| [imagemin-zopfli](https://www.npmjs.com/package/imagemin-zopfli) | png optimisation |

Settings and the compression algorithms are defined and configured in the `imagemin.js` file. Images added to the `src/images` directory are automatically optimised and output to the `images` directory as part of the main `npm run watch` and `npm run build` scripts.