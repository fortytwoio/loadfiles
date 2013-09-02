loadfiles
=========

Load every file from a given directory

```javascript
var fileloader = require("./libs/fileloader")
var loadFilesFor = fileloader(__dirname, 'js')
```


#### An Array with all  Model Objects
var models = loadFilesFor('models')

#### Require all available controllers
var controllers = loadFilesFor('controllers')

#### Require all available middlewares
var middlewares = loadFilesFor('middlewares')

if you have directories like
./models/items.js
./controller/item.js

you may use it like this:
```javascript
controllers.items.get()
models.items.get()
```


