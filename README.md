## Usage

### Given that you have a directory structure like...
```
app/models/items.js
app/controllers/items.js
app/middlewares/auth.js
app/index.js
```


### ...you can then use it like:
```javascript
/* app/index.js */

// require fileloader module
var fileloader = require("loadfiles")

// this inits a load with the basepath set to './app'
var load = fileloader(__dirname, 'js')

// load all '.js' from __dirname + '/models'
var models = load('models')

//load all '.js' from __dirname + '/controllers'
var controllers = load('controllers')

// load all '.js' from __dirname + '/middlewares'
var middlewares = load('middlewares')

// you may then use it like this:
models.items.get()
controllers.items.index(request, response)
middlewares.auth.isAuthenticated('userA')

// or maybe like this
bootstrap(controllers, models, middlewares)
```

### Debug Output
This module uses <https://github.com/visionmedia/debug> for logging. To controll output use these wildcards:
```bash
DEBUG="loadfiles" node index.js
#or
DEBUG="loadfiles:debug" node index.js
```



