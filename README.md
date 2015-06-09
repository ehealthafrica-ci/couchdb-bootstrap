# CouchDB Bootstrap
Bootstrap CouchDB database:

- [x] Configure CouchDB
- [x] Create Databases unless they exist
- [x] Setup `_security` Settings
- [x] Deploy (Design) Documents, Replications and Users

[![Build
Status](https://travis-ci.org/eHealthAfrica/couchdb-bootstrap.svg?branch=master)](https://travis-ci.org/eHealthAfrica/couchdb-bootstrap)


## Directory

```
/path/to/my/project/couchdb
├── _config.json
├── _users
│   ├── alice.json
│   └── bob.json
├── alicedb
│   └── _security.json
└── bobdb
    ├── _design
    │   └── myapp
    │       ├── validate_doc_update.js
    │       └── views
    │           └── by-date
    │               ├── map.js
    │               └── reduce
    └── _security.json
```

See [couchdb-compile](https://github.com/jo/couchdb-compile) for more details about
the CouchDB filesystem mapping used for deploying users, design documents,
normal documents and replications.

## API

```js
var bootstrap = require('couchdb-bootstrap')
bootstrap('http://localhost:5984', 'project/couchdb', function(error, response) {
  // here we go
})
```

## CLI

```sh
couchdb-bootstrap http://localhost:5984 project/couchdb
```

## Tests
```sh
npm test
```
