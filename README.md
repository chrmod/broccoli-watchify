# broccoli-watchify [![Build Status](https://travis-ci.org/eploko/broccoli-watchify.svg)](https://travis-ci.org/eploko/broccoli-watchify)
[![Gitter](https://badges.gitter.im/Join Chat.svg)](https://gitter.im/eploko/broccoli-watchify?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)

The broccoli-watchify plugin bundles your assets with 
[watchify](https://github.com/substack/watchify).

## Installation

```bash
npm install --save-dev broccoli-watchify
```

## Example

```js
var watchify = require('broccoli-watchify');
tree = watchify(tree, options);
```

## API

### watchify(tree, options) 

* `tree`: A [broccoli tree](https://github.com/broccolijs/broccoli#plugin-api-specification) or a directory path as a string

####Options
 
* `entries`: (default `[]`) Array of files to be used as entry points
* `outputFile`: (default `"./browserify.js"`) Output file
* `browserify`: (default `{}`) Options passed to the [browserify constructor](https://github.com/substack/node-browserify#var-b--browserifyfiles-or-opts)
* `require`: (default `[]`) An array of file, option pairs passed to [browserify require method](https://github.com/substack/node-browserify#brequirefile-opts)
* `exclude`: (default `[]`) An array of files passed to [browserify exclude method](https://github.com/substack/node-browserify#bexcludefile)
* `external`: (default `[]`) An array of files passed to [browserify external method](https://github.com/substack/node-browserify#bexternalfile)
* `transform`: (default `[]`) An array of file, option pairs passed to [browserify transform method](https://github.com/substack/node-browserify#btransformtr-opts)
* `cache`: (default `true`) A boolean flag to potentially switch the caching off and act like a plain browserify. Can be helpful in assembling bundles for production and _not_ including all the full local path names in the bundle, which is not possible in the watchify mode.

## Changelog

### 0.2.0

* Expose the `require`, `exclude`, `external` and `transform` properties to further configure the internal browserify instance.

### 0.1.3

* Initial release

## Contributors

The code of this plugin is originally based on the [broccoli-browserify](https://github.com/gingerhendrix/broccoli-browserify) plugin by [Gareth Andrew](http://github.com/gingerhendrix).

## License

The MIT License (MIT). See [LICENSE](LICENSE) for details.

Copyright © 2014 Andrey Subbotin.
