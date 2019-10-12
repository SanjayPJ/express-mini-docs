## PUT and DELETE method

*Install method-override*

```
npm install method-override
```

### app.js

```
var methodOverride = require('method-override')
```

*Add next line after body-parser*

```
app.use(methodOverride('_method'))
```

```
Idea.updateOne({ _id: req.params.id }, { title: req.body.title, details: req.body.details }).then(() => {
        res.redirect('/ideas');
    });
```

```
<form method="POST" action="/resource?_method=DELETE">
  <input type="hidden" name="_method" value="DELETE">
  <button type="submit">Delete resource</button>
</form>
```
