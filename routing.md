## Basic routing

### Get Method

```
app.get('/', function (req, res) {
  res.send('Hello World!')
})
```

### Post method

```
app.post('/', function (req, res) {
  res.send('Got a POST request')
})
```

### Put method

```
app.put('/user', function (req, res) {
  res.send('Got a PUT request at /user')
})
```

### Delete Method

```
app.delete('/user', function (req, res) {
  res.send('Got a DELETE request at /user')
})
```
