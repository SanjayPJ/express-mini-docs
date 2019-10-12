## Template Rendering

*Install express-handlebars*

```
npm install express-handlebars
```

### app.js

```
var express = require('express');
var exphbs  = require('express-handlebars');

var app = express();

app.engine('handlebars', exphbs());
app.set('view engine', 'handlebars');

app.get('/', function (req, res) {
  res.render('home', {
    title: "Home"
  });
});

app.listen(3000);
```

### views/layouts/main.handlebars

```
<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8">
    <title>Example App</title>
</head>
<body>

    {{{body}}}

</body>
</html>
```

### views/home.handlebars

```
<h1>{{ title }}</h1>
```
