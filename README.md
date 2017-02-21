# hapi-error-page [![Build status for hapi-error-page on Circle CI.](https://img.shields.io/circleci/project/sholladay/hapi-error-page/master.svg "Circle Build Status")](https://circleci.com/gh/sholladay/hapi-error-page "Hapi Error Page Builds")

> Friendly error pages for humans.

## Why?

 - Errors in [hapi](https://hapijs.com/) are displayed as [JSON](http://www.json.org/) by default.
 - JSON is good for machines but bad for people.
 - Only transforms user-visible errors.

## Install

```sh
npm install hapi-error-page --save
```

## Usage

Get it into your program.

```js
const errorPage = require('hapi-error-page');
```

Register the plugin on your server.

```js
await server.register(errorPage);
await server.start();
console.log(server.info.uri);
```

Throw or reply with errors as needed.

```js
server.route({
    method : 'GET',
    path   : '/',
    handler(request, reply) {
        throw new Error('uh oh');
    }
})
```

Please use [boom](https://github.com/hapijs/boom) to construct errors instead of `new Error()`, so that we can deliver more useful messages. However, this project will function correctly either way.

## Contributing

See our [contributing guidelines](https://github.com/sholladay/hapi-error-page/blob/master/CONTRIBUTING.md "The guidelines for participating in this project.") for more details.

1. [Fork it](https://github.com/sholladay/hapi-error-page/fork).
2. Make a feature branch: `git checkout -b my-new-feature`
3. Commit your changes: `git commit -am 'Add some feature'`
4. Push to the branch: `git push origin my-new-feature`
5. [Submit a pull request](https://github.com/sholladay/hapi-error-page/compare "Submit code to this project for review.").

## License

[MPL-2.0](https://github.com/sholladay/hapi-error-page/blob/master/LICENSE "The license for hapi-error-page.") © [Seth Holladay](http://seth-holladay.com "Author of hapi-error-page.")

Go make something, dang it.