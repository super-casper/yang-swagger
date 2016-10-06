# yang-swagger

YANG model-driven swagger/openapi transform

  [![NPM Version][npm-image]][npm-url]
  [![NPM Downloads][downloads-image]][downloads-url]

## Installation

```bash
$ npm install -g yang-swagger
```

The preferred installation is *global* for easy access to the
`yang-swagger` utility but can also be used as a dependency module to
help generate swagger/openapi specification as part of your project.

## Quick Start

```bash
$ yang-swagger -f yaml -o swagger.yaml yang-openapi
```

The above example will import the `yang-openapi` YANG module and
transform into swagger specification YAML file.

```
  Usage: yang-swagger [options] modules...

  Options:
      -f, --format <string>    Convert to YAML or JSON (default: json)
      -o, --output <filename>  Write to <filename> if specified, otherwise to console
```

You can also use it as a library module:

```coffeescript
swag = require("yang-swagger").eval {
  'yang-openapi:info':
    title: "my-api"
	description: "describe purpose"
	version: "1.0"
	contact:
	  name: "your name"
	  url: "http://some/website"
	  email: "your email"
	license:
	  name: "Apache-2.0"
}
swag.in('transform')
  .invoke modules: [ 'yang-openapi' ]
  .then (spec) ->
    console.log "do something with <spec>"
```

For more information on programmatic usage, be sure to take a look at
the References listed below.

## References

- [Apiary Documentation](http://docs.yangswagger.apiary.io)
- [Using with Express](http://github.com/corenova/yang-express)
- [Using YANG with JavaScript](http://github.com/corenova/yang-js)

## License
  [Apache 2.0](LICENSE)

This software is brought to you by
[Corenova Technologies](http://www.corenova.com). We'd love to hear
your feedback.  Please feel free to reach me at <peter@corenova.com>
anytime with questions, suggestions, etc.

[npm-image]: https://img.shields.io/npm/v/yang-swagger.svg
[npm-url]: https://npmjs.org/package/yang-swagger
[downloads-image]: https://img.shields.io/npm/dt/yang-swagger.svg
[downloads-url]: https://npmjs.org/package/yang-swagger
