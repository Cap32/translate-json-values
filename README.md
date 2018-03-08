# neo-json-i18n

[![CircleCI](https://circleci.com/gh/Cap32/neo-json-i18n.svg?style=shield)](https://circleci.com/gh/Cap32/neo-json-i18n)
[![Build Status](https://travis-ci.org/Cap32/neo-json-i18n.svg?branch=master)](https://travis-ci.org/Cap32/neo-json-i18n)
[![Build status](https://ci.appveyor.com/api/projects/status/itq4dp7186526wcl?svg=true)](https://ci.appveyor.com/project/Cap32/neo-json-i18n)
[![Coverage Status](https://coveralls.io/repos/github/Cap32/neo-json-i18n/badge.svg?branch=master)](https://coveralls.io/github/Cap32/neo-json-i18n?branch=master)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](http://makeapullrequest.com)
[![License](https://img.shields.io/badge/license-MIT_License-blue.svg?style=flat)](https://github.com/Cap32/neo-json-i18n/blob/master/LICENSE.md)

Translate json files over google translate

## Installation

#### Via yarn

```shell
$ yarn global add neo-json-i18n
```

#### Via npm

```shell
$ npm install -g neo-json-i18n
```

## CLI Usage

```shell
$ neo-json-i18n <src> [options]
```

### Options

```js
output: {
    alias: 'o',
    describe: 'Output directory',
    type: 'string',
},
lang: {
    alias: 'l',
    type: 'array',
    describe: 'Languages',
    default: ['en'],
},
pattern: {
    alias: 'p',
    type: 'string',
    describe: 'Output file name pattern',
    default: '$name_$lang.$ext',
},
cwd: {
    alias: 'd',
    type: 'string',
    describe: 'Current working directory',
    default: process.cwd(),
},
spaces: {
    alias: 's',
    type: 'string',
    describe: 'JSON format spaces',
    default: '  ',
},
```

### Example

**~/my/repo/dict.json**

```json
{ "film": "Star Wars" }
```

`cd ~/my/repo/` and run `neo-json-i18n dict.json --lang zh-cn`, it would create
a `dict_zh-cn.json` file

**~/my/repo/dict_zh-cn.json**

```json
{ "film": "星球大战" }
```

## Node Module API Usage

```js
import jsonI18n from "neo-json-i18n";
const json = { film: "Star Wars" };
jsonI18n(json, { lang: ["zh-cn"] })
    .then(res => console.log(res))
    .catch(err => console.error(err));
/*
  output: { 'zh-cn': { film: '星球大战' } }
 */
```

output:

## License

MIT
