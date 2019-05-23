# SCSS
The codekit provides a way to compile sass/scss files into css via [node-sass](https://github.com/sass/node-sass). Node-sass is a library that provides binding for Node.js to LibSass, the C version of the popular stylesheet preprocessor, Sass. It allows you to natively compile .scss files to css at incredible speed and automatically via a connect middleware.


## Scripts for scss
The `package.json` includes the following commands and tasks:

| Task | Description |
| --- | --- |
| `npm run build` | `npm run build` compiles files into their build directories ready for use in a production environment. `.scss` files are linted, then compiled using the minify script (below) & then run through the postcss autoprefixer function. |
| `npm run watch` | Watches for changes to `.scss` files in `/src/scss` compiles them for development purposes.|
| `npm run scss:dev` | will compile all `.scss` files for development purposes, with code expanded, comments included & including mappings to the source files to make debugging simplier. |
| `npm run scss:prod` | will compile all `.scss` files for production purpose, comments and unnecessary code is removed and the file is minified. |
| `npm run autoprefixer` | will parse any `.css` file in the `/css` directory and add vendor prefixes to CSS rules using values from [Can I Use](https://caniuse.com) |

The scss scripts are configured to take `.scss` files in the `/src/scss` directory and builds / compiles them to a `/css` directory (if the directory does not exist, it will be created).

## Autoprefixer

The codekit uses [Autoprefixer][autoprefixer] (included in the build process) to automatically add vendor prefixes to some CSS properties at build time. Doing so saves time and code by allowing us to write key parts of our CSS a single time while eliminating the need for vendor mixins.

We maintain the list of browsers supported through Autoprefixer in a separate file within our GitHub repository. See [package.json](/package.json) for details.

[autoprefixer]: https://github.com/postcss/autoprefixer