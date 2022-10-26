# API Documentation (Cello Exercise Index)

# Implemented
## Get a list of all books 
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


## Get a list of all tags
```
GET /api/tag
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

## Get a list of exercises
``` 
GET /api/exercise
```
Example response: /api/exercise/1
```
[
    {
        "id": 1
        "page_and_exercise": "pg. 50 Exercise for the Right Hand",
        "tags":  [{"level": 1, "tag_name": "Stacatto"}, 
                  {"level": 2, "tag_name": "Spicatto}],
        "book": {
            "id": 2,
            "title": "Book 2",
            "author": "Author 2",
            "date": "1990",
            "link": "www.book.com"
        }
    },
    {
        "id": 2
        "page_and_exercise": "pg. 50 Exercise in thirds",
        "tags":  [{"level": 1, "tag_name": "Stacatto"}, 
                  {"level": 2, "tag_name": "Spicatto}],
        "book": {
            "id": 2,
            "title": "Book 2",
            "author": "Author 2",
            "date": "1990",
            "link": "www.book.com"
        }
    },
    ...
]
```
# Subject to change

# Not implemented yet - TO DO

## Get a list of all tags for a given level - RACHEL
```
GET /api/tag/level/<levelnum>
```
Example response: /api/tag/level/1
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

## Get a list of 50 exercises starting from num 
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
        "book": {
            "id": 2,
            "title": "Book 2",
            "author": "Author 2",
            "date": "1990",
            "link": "www.book.com"
        }
    },
    {
        "id": 2
        "page_and_exercise": "pg. 50 Exercise in thirds",
        "tags":  [{"level": 1, "tag_name": "Stacatto"}, 
                  {"level": 2, "tag_name": "Spicatto}],
        "book": {
            "id": 2,
            "title": "Book 2",
            "author": "Author 2",
            "date": "1990",
            "link": "www.book.com"
        }
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
    "page_and_exercise": "pg. 2 exercise 1"
    "book_id": 2,
    "book_title": "Title 2"
    "author": "Mr. Author",
    "date": "2019"
    "tags": [{"id": 1, "level": 1, "tag_name": "Stacatto"}, 
             {"id": 1, "level": 2, "tag_name": "Spicatto}],
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
        "book_title": "Title 1"
        "author": "Author1",
        "date": "2017",
    },
    {
        "id": 3
        "page_and_exercise": "pg. 50 Exercise in thirds",
        "tags":  [{"id": 1, "level": 1, "tag_name": "Stacatto"}, 
                  {"id": 1, "level": 2, "tag_name": "Spicatto}],
        "book_id": 3,
        "book_title": "Title 3",
        "author": "Author 1",
        "date": "2017"
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
        "book_title": "Title 1",
        "author": "Author 1",
        "date": "2017"
    },
    {
        "id": 3
        "page_and_exercise": "pg. 50 Exercise in thirds",
        "tags":  [{"id": 1, "level": 1, "tag_name": "Stacatto"}, 
                  {"id": 2, "level": 2, "tag_name": "Spicatto}],
        "book_id": 3,
        "book_title": "Title 3",
        "author": "Author 1",
        "date": "2017"
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

# Requires authentication (admin permissions)
## Add a book to the table - REBECCA
```
POST /api/book
```
Parameters:

Name | Type | Mandatory | Description
------------ | ------------ | ------------ | ------------
title | STRING | YES | 
author | STRING | YES |
date | STRING | YES | Date that the book was published
link | STRING | YES |

## Add a tag to the table - REBECCA
```
POST /api/tag
```
Name | Type | Mandatory | Description
------------ | ------------ | ------------ | ------------
level | STRING | YES | Tag level (for now just 1, 2, or 3)
tag_name | STRING | YES |


## Add exercise information about a single exercise to the table - REBECCA
```
POST /api/exerciseinfo
```
Name | Type | Mandatory | Description
------------ | ------------ | ------------ | ------------
side | STRING | YES | 
tenor | BOOLEAN | YES |
treble | BOOLEAN | YES |
book_id | INTEGER | YES | The book ID to which this exercise belongs
page_and_exercise | STRING | YES

## Add an exercise and its tag to the database - REBECCA
```
POST /api/exercise
```
Name | Type | Mandatory | Description
------------ | ------------ | ------------ | ------------
exercise_id | INTEGER | YES | 
tag_id | INTEGER | YES
