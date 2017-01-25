Mongoose Connection Ready
=========================

[![Greenkeeper badge](https://badges.greenkeeper.io/mjlescano/mongoose-connection-ready.svg)](https://greenkeeper.io/)

Helper function to get a Promise from a Mongoose `connection` object.

Usage
=====

```
npm install mongoose-connection-ready --save
```

```javascript
var mongoose = require('mongoose')
var connReady = require('mongoose-connection-ready')

mongoose.connect('mongodb://localhost/dev')

connReady(mongoose.connection)
  .then(function () {
    console.log('Mongo connected successfully!')
  })
  .catch(function () {
    console.error('Couldn\'t connect to Mongo.')
    mongoose.connection.close(function () {
      process.exit(1)
    })
  })
```
