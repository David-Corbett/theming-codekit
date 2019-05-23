# Documentation

Running our documentation locally requires the use of [MkDocs](https://www.mkdocs.org). MkDocs is a fast, simple and downright gorgeous static site generator that's geared towards building project documentation. Documentation source files are written in Markdown, and configured with a single YAML configuration file. We use MkDocs to build a static HTML site that we host on GitLab pages.

There's a stack of good looking themes available for MkDocs. The `mkdocs.yml` file in the repository is configured to use the [Material for MkDocs](https://squidfunk.github.io/mkdocs-material) theme.

## Getting started
It is possible to install MkDocs a package manager (such as apt-get, dnf, homebrew, yum, chocolatey, etc.). However this can pose some compatibility issues, particularly on Mac OSX.