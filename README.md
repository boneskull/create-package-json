# Create a `package.json` like a champion

[![NPM Version](https://badgen.net/npm/v/create-package-json?icon=npm)](https://npmjs.org/package/create-package-json)
[![NPM Downloads](https://badgen.net/npm/dm/create-package-json?icon=npm)](https://npmjs.org/package/create-package-json)
[![JS Standard Style](https://badgen.net/badge/code%20style/standard/blue)](https://github.com/standard/standard)
[![GitHub Sponsor](https://badgen.net/badge/icon/sponsor/pink?icon=github&label=github)](https://github.com/sponsors/wesleytodd)

This is a fully featured `package.json` scaffolding tool.  It goes above and beyond the basic `npm init`
by supporting (almost) all of the keys you can set in a `package.json`.  It can be used as a simple cli
tool, or inside your other package scaffolding tools.

*NOTE:* This is a work in progress, more to come on docs and there are some missing options at the moment.
[See here](https://github.com/wesleytodd/create-package-json/blob/master/index.js#L14-L27) for missing fields.

## Usage

```
$ npm init package-json
$ npx create-package-json

# or

$ npm install -g create-package-json
$ create-package-json
```

### CLI Usage

```
$ create-package-json --help

create-package-json

Create a package.json

Options:
  --help               Show help                                       [boolean]
  --version            Show version number                             [boolean]
  --no-prompt          Prompts, --no-prompt to use defaults and input only
                                                                       [boolean]
  --directory, -d      Working directory                                [string]
  --silent, -S         Suppress all output                             [boolean]
  --advanced           Show advanced prompts                           [boolean]
  --existing-package                                                    [string]
  --scope                                                               [string]
  --scripts                                                             [string]
  --name                                                                [string]
  --package-version                                                     [string]
  --description                                                         [string]
  --author                                                              [string]
  --repository                                                          [string]
  --keywords                                                            [string]
  --license                                                             [string]
  --type                                                                [string]
  --main                                                                [string]
  --private                                                            [boolean]
  --dependencies                                                        [string]
  --dev-dependencies                                                    [string]
  --peer-dependencies                                                   [string]
  --test                                                                [string]
  --prepare                                                             [string]
  --post-publish                                                        [string]
  --pre-version                                                         [string]
  --spacer                                                              [string]
  --ignore-existing                                                    [boolean]
  --save-exact                                                         [boolean]
```

Dependencies should be a comma separated list like `--dependencies="express,react"`, and it can also
include versions, `--dependencies="express@5"`.

Scripts should be defined as a json string, `--scripts='{"test":"exit 0"}'`.

### Programmatic Usage

```javascript
const createPackageJson = require('create-package-json')

;(async () => {
  const pkg = await createPackageJson({
    name: '@myscope/my-package',
    description: 'A useless new package',
    dependencies: ['express'],
    devDependencies: ['mocha'],
    author: 'Me <me@me.com>',
    version: '1.0.0'
  })

  console.log(pkg) // The json after writing and installing
})()
```
