**DocuAPI** is a beautiful multilingual API documentation theme for [Hugo](http://gohugo.io/). This theme is built on top of the beautiful work of [Robert Lord](https://github.com/lord) and others on the [Slate](https://github.com/lord/slate) project ([Apache 2 License](https://github.com/lord/slate/blob/master/LICENSE)).

<br/>

> Visit the [demo site](http://docuapi.com/).

<br/>

![Build Status](https://circleci.com/gh/bep/docuapi.svg?style=shield&circle-token=:circle-ci-badge-token)

![Screenshot DocuAPI Example site](https://raw.githubusercontent.com/bep/docuapi/master/images/screenshot.png)

## Use

See the [exampleSite](https://github.com/bep/docuapi/tree/master/exampleSite) and more specific its site [configuration](https://github.com/bep/docuapi/blob/master/exampleSite/config.toml) for the available options.

**Note that this theme needs Pygments installed to render code samples. See [pygments.org](http://pygments.org/)**

**Most notable:** This theme will use all the (non drafts) pages in the site and build a single-page API documentation. Using `weight` in the page front matter is the easiest way to control page order.

If you want a different page selection, please provide your own `layouts/index.html` template.

## Develop the Theme

**Note:** In most situations you will be well off just using the theme and maybe in some cases provide your own template(s). Please refer to the [Hugo Documentation](http://gohugo.io/overview/introduction/) for that.

But you may find styling issues, etc., that you want to fix. Pull requests of this type is welcomed.

**If you find issues that obviously belongs to  [Slate](https://github.com/lord/slate), then please report/fix them there, and we will pull in the latest changes here when that is done.**

This project provides a very custom asset bundler in [bundler.go](https://github.com/bep/docuapi/blob/master/bundler.go) written in Go.

It depends on `libsass` to build, so you will need `gcc` (a C compiler) to build it for your platform. If that is present, you can try:

* `go get -u -v .`
* `go run bundler.go` (this will clone Slate to a temp folder)
* Alternative  to the above if you already have Slate cloned somewhere: `go run bundler.go -slate=/path/to/Slate`

All options:

```bash
go run bundler.go -h
  -minify
    	apply minification to output Javascript, CSS etc. (default true)
  -slate string
    	the path to the Slate source, if not set it will be cloned from https://github.com/lord/slate.git
```

With `make` and `fswatch` (OSX only, I believe) available, you can get a fairly enjoyable live-reloading development experience for all artifacts by running:

* `hugo server` in your Hugo site project.
* `make serve` in the theme folder.




