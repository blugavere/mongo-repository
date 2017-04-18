# Mongo Repository
[![NPM version][npm-image]][npm-url][![dependencies Status](https://david-dm.org/blugavere/mongo-repository/status.svg)](https://david-dm.org/blugavere/mongo-repository) [![Coverage Status](https://coveralls.io/repos/github/blugavere/mongo-repository/badge.svg?branch=master)](https://coveralls.io/github/blugavere/mongo-repository?branch=master)[![NPM Downloads](https://img.shields.io/npm/dm/mongo-repository.svg?style=flat)](https://www.npmjs.com/package/mongo-repository)[![Build Status](https://travis-ci.org/blugavere/mongo-repository.svg?branch=master)](https://travis-ci.org/blugavere/mongo-repository)[![Patreon](https://img.shields.io/badge/patreon-support%20the%20author-blue.svg)](https://www.patreon.com/blugavere)

## Installation 

```sh
$ npm install --save mongo-repository
```

## Usage

```js

'use strict'

const MongoRepository = require('mongo-repository');

class CatRepository extends MongoRepository {
  constructor(db, modelName) {
    super(db, modelName);
  }
}

// or if you dont need custom functionality

const repo = new MongoRepository(db, modelName);
```

## Getting Started

```js

'use strict';

const MongoClient = require('mongodb').MongoClient;

// configure a collection name
const collection = 'cats';
const MongoRepository = require('mongo-repository');

let repo;

// connect to mongodb
MongoClient.connect('mongodb://localhost', (err, db) => {

  // construct a repo
  repo = new MongoRepository(db, collection);

  repo.add({name:'Fido'}, (err, data) => {
    console.log(data);
    repo.disconnect();
  });
}

```


## License

MIT © [Ben Lugavere](http://benlugavere.com/)


[npm-image]: https://badge.fury.io/js/mongo-repository.svg
[npm-url]: https://npmjs.org/package/mongo-repository
[travis-image]: https://travis-ci.org/blugavere/mongo-repository.svg?branch=master
[travis-url]: https://travis-ci.org/blugavere/mongo-repository
[daviddm-image]: https://david-dm.org/blugavere/mongo-repository.svg?theme=shields.io
[daviddm-url]: https://david-dm.org/blugavere/mongo-repository
[coveralls-image]: https://coveralls.io/repos/blugavere/mongo-repository/badge.svg
[coveralls-url]: https://coveralls.io/r/blugavere/mongo-repository
