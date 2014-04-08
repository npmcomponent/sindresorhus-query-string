*This repository is a mirror of the [component](http://component.io) module [sindresorhus/query-string](http://github.com/sindresorhus/query-string). It has been modified to work with NPM+Browserify. You can install it using the command `npm install npmcomponent/sindresorhus-query-string`. Please do not open issues or send pull requests against this repo. If you have issues with this repo, report it to [npmcomponent](https://github.com/airportyh/npmcomponent).*
# query-string [![Build Status](https://travis-ci.org/sindresorhus/query-string.svg?branch=master)](https://travis-ci.org/sindresorhus/query-string)

> Parse and stringify URL [query strings](http://en.wikipedia.org/wiki/Query_string)


## Install

Download [manually](https://github.com/sindresorhus/query-string/releases) or with a package-manager.

```bash
$ npm install --save query-string
```

```bash
$ bower install --save query-string
```

```bash
$ component install sindresorhus/query-string
```


## Usage

```js
console.log(location.search);
// ?foo=bar

var parsed = queryString.parse(location.search);
console.log(parsed);
// {foo: 'bar'}

parsed.foo = 'unicorn';
parsed.ilike = 'pizza';
location.search = queryString.stringify(parsed);

console.log(location.search);
// ?foo=unicorn&ilike=pizza
```


## API

### queryString.parse(*string*)

Parse a query string into an object.

### queryString.stringify(*object*)

Stringify an object into a query string.


## Nesting

This module intentionally doesn't support nesting as it's not specced and varies between implementations, which causes a lot of [edge cases](https://github.com/visionmedia/node-querystring/issues).

You're much better off just converting the object to a JSON string:

```js
queryString.stringify({
  foo: 'bar',
  nested: JSON.stringify({
    unicorn: 'cake'
  })
});
// foo=bar&nested=%7B%22unicorn%22%3A%22cake%22%7D
```


## License

[MIT](http://opensource.org/licenses/MIT) © [Sindre Sorhus](http://sindresorhus.com)
