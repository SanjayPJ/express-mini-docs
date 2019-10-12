## MongoDB - Mongoose

*Install mongoose*

```
npm install mongoose
```

#### app.js

```
let mongoose = require('mongoose');

mongoose.connect('mongodb://localhost/vidjot', { useNewUrlParser: true })
  .then(() => console.log("MongoDB Connected"))
  .catch(err => console.log(err));
```

### Creating Model

*create `models/Model.js`*

#### Model.js

```
var mongoose = require('mongoose');
const Schema = mongoose.Schema;

const IdeaSchema = new Schema({
  title: {
    type: string,
    required: true
  },
  details: {
    type: string,
    required: true
  },
  date: {
    type: Date,
    default: Date.now()
  }
});

mongoose.model('Ideas', IdeaSchema);
```

#### app.js

```
require('./models/Idea');
const Idea = mongoose.model("Ideas");
```