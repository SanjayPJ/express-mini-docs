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
Idea.findOne({
      _id: req.params.id
  })
  .then(idea => {
      idea.title = req.body.title;
      idea.details = req.body.details;

      idea.save().then(idea => {
          res.redirect('/ideas');
      });
  })
```

```
<form method="POST" action="/resource?_method=DELETE">
  <input type="hidden" name="_method" value="DELETE">
  <button type="submit">Delete resource</button>
</form>
```
