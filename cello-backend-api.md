# API Documentation (Cello Exercise Index)

# Implemented
Currently nothing!

# Subject to change
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

# Not implemented yet - TO DO
## Get a list of all books (same as above, but we need to include ID) - RACHEL
```
GET /api/book
```
Example response:
```
[
    {   
        "id": 1,
        "title": "Title 1",
        "author": "Author 1",
        "date": "2019",
        "link": "www.test.com"
    },
    {
        "id": 2,
        "title": "Title 2",
        "author": "Author 2",
        "date": "2019",
        "link": "www.book2.com"
    }
]
```

## Get a list of all tags for a given level - RACHEL
```
GET /api/tags/<levelnum>
```
Example response: /api/tags/1
```
[
    {
        "id": 1,
        "level": 1,
        "tag_name": "Spicatto"
    },
    {   
        "id": 2,
        "level": 1,
        "tag_name": "Arpeggios"
    }
]
```

## Get a list of 50 exercises starting from num - BENJAMIN
``` 
GET /api/exercise/<num>
```
Example response: /api/exercise/1
```
[
    {
        "id": 1
        "page_and_exercise": "pg. 50 Exercise for the Right Hand",
        "tags":  [{"level": 1, "tag_name": "Stacatto"}, 
                  {"level": 2, "tag_name": "Spicatto}],
        "book_id": 1,
        "book_name": "Title 1",
        "author": "Author 1"
    },
    {
        "id": 2
        "page_and_exercise": "pg. 50 Exercise in thirds",
        "tags":  [{"level": 1, "tag_name": "Stacatto"}, 
                  {"level": 2, "tag_name": "Spicatto}],
        "book_id": 2,
        "book_name": "Title 2",
        "author": "Author 2"
    },
    ...
]
```

## Get the exercise info of an exercise - EREN
``` 
GET /api/exerciseinfo/<num>
```
Example response: /api/exercise/1
```
{
    "id": 1,
    "side": "Right side",
    "tenor": true,
    "treble": false,
    "book_id": 2,
    "book_name": "Title 2"
}
```

## Get all exercises by author name - EREN
``` 
GET /api/exercise/author/<authorname>
```
Example response: /api/exercise/Author1
```
[
    {
        "id": 1
        "page_and_exercise": "pg. 50 Exercise for the Right Hand",
        "tags":  [{"id": 1, "level": 1, "tag_name": "Stacatto"}, 
                  {"id": 2, "level": 2, "tag_name": "Spicatto}],
        "book_id": 1,
        "book_name": "Title 1"
        "author": "Author1"
    },
    {
        "id": 3
        "page_and_exercise": "pg. 50 Exercise in thirds",
        "tags":  [{"id": 1, "level": 1, "tag_name": "Stacatto"}, 
                  {"id": 1, "level": 2, "tag_name": "Spicatto}],
        "book_id": 3,
        "book_name": "Title 3",
        "author": "Author 1"
    },
    ...
]
```

## Get all exercises with tag id(s) - EREN
```
GET /api/exercise/tag/<tags>
```
Example response: /api/exercise/tag/1
```
[
    {
        "id": 1
        "page_and_exercise": "pg. 50 Exercise for the Right Hand",
        "tags":  [{"id": 1, "level": 1, "tag_name": "Stacatto"}]
        "book_id": 1,
        "book_name": "Title 1"
        "author": "Author 1"
    },
    {
        "id": 3
        "page_and_exercise": "pg. 50 Exercise in thirds",
        "tags":  [{"id": 1, "level": 1, "tag_name": "Stacatto"}, 
                  {"id": 2, "level": 2, "tag_name": "Spicatto}],
        "book_id": 3,
        "book_name": "Title 3",
        "author": "Author 1"
    },
    ...
]
```

## Get list of all authors - RACHEL
```
GET /api/author
```
```
{"authors": ["Author 1", "Author 2", "Third Author"]}
```
