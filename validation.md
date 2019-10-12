## Server Side Form Validation

*install body-parser*

```
npm install body-parser
```

#### app.js

```
var bodyParser = require('body-parser')
```

```
app.use(bodyParser.urlencoded({ extended: false }))
app.use(bodyParser.json())
```

### Validation

```
let errors = [];

if(!req.body.title){
  errors.push({text: 'Title is required.'})
}

if(!req.body.details){
  errors.push({text: 'Details is required.'})
}

if(errors.length > 0){
  res.render('add', {
    errors: errors,
    title: req.body.title,
    details: req.body.details
  })
}else{
  res.send("pass");
}
```
