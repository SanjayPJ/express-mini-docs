# Flash Messaging

```
npm install connect-flash
npm install express-session
```

### app.js

```
const flash = require('connect-flash');
const session = require('express-session')

app.use(session({
    secret: 'keyboard cat',
    resave: true,
    saveUninitialized: true,
}))

app.use(flash());

app.use((req, res, next) => {
    res.locals.success_msg = req.flash('success_msg');
    res.locals.error_msg = req.flash('error_msg');
    res.locals.error = req.flash('error');
    next();
})
```

*inside partials create _msg.handlebars*

```
{{# if success_msg}}
<div class="alert alert-success mt-2">
	{{success_msg}}
</div>
{{/if}}

{{# if error_msg}}
<div class="alert alert-danger mt-2">
	{{error_msg}}
</div>
{{/if}}
```

*Trigger it using*

```
req.flash('error_msg', 'Idea deleted successfully')
req.flash('success_msg', 'Idea deleted successfully')
```
