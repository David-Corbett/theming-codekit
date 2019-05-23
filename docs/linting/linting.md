# Linting tools
The codekit provides linting for `.js` and `.scss` files, to ensure compliance with coding standards.

## Using NPM scripts
The `package.json` includes the following commands and tasks:

| Task | Description |
| --- | --- |
| `npm run lint`  | Will run all `.scss` and `.js` files through their respective linting tools - [eslint]() & [sass-lint](https://github.com/sasstools/sass-lint) |
| `npm run lint-scss`  | Will run all `.scss` files through [sass-lint](https://github.com/sasstools/sass-lint). The command can also accept a parameter to lint an individual file. To do this `npm run lint-scss -- scssfile:name-of-file` where `name-of-file` is the file you want to lint relative to the package.json for the project. **NB** space after `-- ` before the `scssfile` variable is passed.   |

## SCSS Linting
[Sass-lint](https://github.com/sasstools/sass-lint) is a node only linter for both `sass` and `scss` syntax. Sass-lint is configured from a `.sass-lint.yml` or `.scsslintrc` file in the project. A `.sass-lint.yml` with sensible defaults is provided as part of the codekit. If you don't have either file in the root of your project or you would like all your projects to follow a standard config file then you can specify the path to one in your project's package.json file with the `sasslintConfig` option.

For example:
```json
{
  "name": "my-project",
  "version": "1.0.0",
  "config": {
      "sasslintConfig": "PATH/TO/YOUR/CONFIG/FILE"
    }
}
```
### Rules

For all [rules](https://github.com/sasstools/sass-lint/tree/master/docs/rules), setting their severity to 0 turns it off, setting to 1 sets it as a warning (something that should not be committed in), and setting to 2 sets it to an error (something that should not be written). If a rule is set to just a severity, it will use the default configuration (where available).

The severity of the warning(s) will have an impact on the console output - it is important to scroll up and read the output from where the command was invoked. For more severe warnings, the end of the console output might look like this
```console
npm ERR! A complete log of this run can be found in:
npm ERR!     /Users/username/.npm/_logs/2019-05-15T13_41_42_641Z-debug.log
``` 

Special comments can be used to disable and enable certain rules throughout your source files in a variety of scenarios. These can be useful when dealing with legacy code or with certain necessary code smells. You can read the documentation for this feature [here](https://github.com/sasstools/sass-lint/tree/master/docs/toggle-rules-in-src.md).

Below are examples of how to use this feature:


### Disable a rule for the entire file

```scss
// sass-lint:disable border-zero
p {
  border: none; // No lint reported
}
```

### Disable more than 1 rule

```scss
// sass-lint:disable border-zero, quotes
p {
  border: none; // No lint reported
  content: "hello"; // No lint reported
}
```

### Disable a rule for a single line

```scss
p {
  border: none; // sass-lint:disable-line border-zero
}
```

### Disable all lints within a block (and all contained blocks)

```scss
p {
  // sass-lint:disable-block border-zero
  border: none; // No result reported
}

a {
  border: none; // Failing result reported
}
```

### Disable and enable again

```scss
// sass-lint:disable border-zero
p {
  border: none; // No result reported
}
// sass-lint:enable border-zero

a {
  border: none; // Failing result reported
}
```

### Disable/enable all linters

```scss
// sass-lint:disable-all
p {
  border: none; // No result reported
}
// sass-lint:enable-all

a {
  border: none; // Failing result reported
}
```

