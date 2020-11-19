# Configuring dynamic mapping

## Disable dynamic mapping
```
PUT /people
{
  "mappings": {
    "dynamic": false,
    "properties": {
      "first_name": {
        "type": "text"
      }
    }
  }
}
```

## Set dynamic mapping to `strict`
```
PUT /people
{
  "mappings": {
    "dynamic": "strict",
    "properties": {
      "first_name": {
        "type": "text"
      }
    }
  }
}
```

## Index a test document
```
POST /people/_doc
{
  "first_name": "Noureddin",
  "last_name": "Sadawi"
}
```

## Retrieve mapping
```
GET /people/_mapping
```

## Search `first_name` field
```
GET /people/_search
{
  "query": {
    "match": {
      "first_name": "Noureddin"
    }
  }
}
```

## Search `last_name` field
```
GET /people/_search
{
  "query": {
    "match": {
      "last_name": "Sadawi"
    }
  }
}
```

## Clean up
```
DELETE /people
```