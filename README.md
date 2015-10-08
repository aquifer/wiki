# Introduction to Aquifer
This is the documentation for the [Aquifer](https://github.com/aquifer/aquifer) project:

* [Github org](https://github.com/aquifer)
* [Aquifer core](https://github.com/aquifer/aquifer)

## Table of Contents
* [What is a 'Drush make workflow'?](sections/what-is-a-drush-make-workflow.md)
* [What is Aquifer?](sections/what-is-aquifer.md)

## Contributing
Contributing to this wiki is painless. Everything is stored and served from the [Aquifer wiki](http://github.com/aquifer/wiki) repository.
All pages are stored in the `/sections` folder, and added to the `SUMMARY.md` file as markdown links in a bulleted list. [Gitbook](https://github.com/GitbookIO/gitbook) is used to compile the docs and create the browser-friendly pages, which is published on Github pages at [docs.aquifer.io](http://docs.aquifer.io).

### Process for submitting changes
* Fork the [Aquifer wiki](http://github.com/aquifer/wiki) repository.
* Make your changes in a branch other than `master` or `gh-pages`.
* Submit a PR with your changes.

### Using gitbook
This wiki uses gitbooks to compile the markdown files into a collection of browser-friendly pages. To compile the markdown:

* Install gitbook: `npm install gitbook-cli -g`.
* In the wiki directory, run `gitbook build`.
* If you would like to locally test the compiled output, run `gitbook serve`, and point your browser at `http://localhost:4000`.
