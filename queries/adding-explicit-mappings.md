# Adding explicit mappings

## Add field mappings for `reviews` index
```
PUT /reviews
{
  "mappings": {
    "properties": {
      "rating": { "type": "float" },
      "content": { "type": "text" },
      "product_id": { "type": "integer" },
      "author": {
        "properties": {
          "first_name": { "type": "text" },
          "last_name": { "type": "text" },
          "email": { "type": "keyword" }
        }
      }
    }
  }
}
```

## Index a test document
```
PUT /reviews/_doc/1
{
  "rating": 5.0,
  "content": "Great course! I have learned a lot about Elasticsearch!",
  "product_id": 123,
  "author": {
    "first_name": "Jane",
    "last_name": "Baker",
    "email": "janebaker@example.com"
  }
}
```