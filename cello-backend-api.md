# API Documentation (Cello Exercise Index)

## Get a list of all books 
```
GET /api/book
```
Example response:
```
[
    {
        "title": "Title 1",
        "author": "Author 1",
        "date": "2019",
        "link": "www.test.com"
    },
    {
        "title": "Title 2",
        "author": "Author 2",
        "date": "2019",
        "link": "www.book2.com"
    }
]
```

## Get a list of all tags
```
GET /api/tags
```
Example response:
```
[
    {
        "level": 1,
        "tag_name": "Spicatto"
    },
    {
        "level": 2,
        "tag_name": "Staccato"
    }
]
```

## Other stuff coming soon!