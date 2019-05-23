# Build Tools
## Installation
The codekit uses [NPM scripts](https://docs.npmjs.com/misc/scripts) and packages to create tooling that a developer would ideally like to have for theming web content. Therefore to get started, the developer must have NPM installed on their machine. To see if you already have Node.js and npm installed, check the installed version, run the following commands in a terminal window:
```console
node -v
npm -v
``` 
Both commands should return a version number similar to `v10.x.x` or `6.x.x` (where x is a valid integer). More information on installing NPM on various platforms and devices is available on the [NPM website](https://docs.npmjs.com/downloading-and-installing-node-js-and-npm).

When you are sure that Node.js and npm are installed on the machine, open a terminal and navigate to the root directory of the project where the `package.json` file is located and run `npm install`to install our local dependencies listed in [package.json](/package.json). 

## Tooling setup
With the codekit using [NPM scripts](https://docs.npmjs.com/misc/scripts) for its build system, the `package.json` includes convenient methods for working with the framework, including compiling code, running tests, and more.

### Using NPM scripts
The `package.json` includes the following commands and tasks:

| Task | Description |
| --- | --- |
| `npm run build` | `npm run build` compiles files into their build directories ready for use in a production environment. **Uses [Sass](https://sass-lang.com/), [Autoprefixer][autoprefixer], and [UglifyJS](https://github.com/mishoo/UglifyJS2).** |
| `npm run watch` | Watches for changes to scss and js files & compiles them for development purposes.|
| `npm run lint`  | Will run all `.scss` and `.js` files through their respective linting tools - [eslint]() & [sass-lint](https://github.com/sasstools/sass-lint) |
| `npm run lint-scss`  | Will run all `.scss` files through [sass-lint](https://github.com/sasstools/sass-lint). The command can also accept a parameter to lint an individual file. To do this `npm run lint-scss -- scssfile:name-of-file` where `name-of-file` is the file you want to lint relative to the package.json for the project. |
| `npm run docs-serve` | Starts a local server to view documentation on and will automatically update as changes are saved. |

Run `npm run` to see all the npm scripts.

## Troubleshooting

Should you encounter problems with installing dependencies, uninstall all previous dependency versions (global and local). Then, rerun `npm install`.

[autoprefixer]: https://github.com/postcss/autoprefixer
