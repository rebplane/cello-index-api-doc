# API Documentation (Cello Exercise Index)

## Table of contents
- [Books](#Books)
- [Tags](#Tags)
- [Exercises](#Exercises)

# Implemented
# Books <a name="Books"></a>
## Methods:
```
GET /api/book
GET /api/book/<book_id>
GET /api/author
POST /api/book
```
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
## Get information for a single book
``` 
GET /api/book/<book_id>
```
Example response: /api/book/1
```
{   
    "id": 1,
    "title": "Title 1",
    "author": "Author 1",
    "date": "2019",
    "link": "www.test.com"
}
```

## Get list of all authors 
```
GET /api/author
```
```
{"authors": ["Author 1", "Author 2", "Third Author"]}
```

# Tags <a name="Tags"></a>
## Methods:
```
GET /api/tag
GET /api/tag/<tag_id>
GET /api/tag/exercise/<exercise_id>
POST /api/tag
```
## Get a list of all tags
```
GET /api/tag
```
Example response: /api/tag
```
[
    {
        "id": 1,
        "level": 1,
        "tag_name": "Spicatto"
    },
    {
        "id": 2,
        "level": 2,
        "tag_name": "Staccato"
    }
]
```

## Get information for a tag
``` 
GET /api/tag/<tag_id>
```
Example response: /api/tag/1
```
{
    "id": 1,
    "level": 1,
    "tag_name": "Spicatto"
}
```

## Get a list of all tags for a given level 
```
GET /api/tag/level/<level_num>
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

## Get a list of all tags for an exercise
```
GET /api/tag/exercise/<exercise_id>
```
Example response: /api/tag/exercise/<exercise_id>
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


# Exercises <a name="Exercises"></a>
## Methods:
```
GET /api/exerciseinfo
GET /api/exerciseinfo/<num>
POST /api/exerciseinfo
```
## Get a list of all exercises
``` 
GET /api/exerciseinfo
```
Example response: /api/exerciseinfo
```
[
    {
        "id": 1,
        "side": "Left Side",
        "page_and_exercise": "pg. 11 Exercise 10",
        "tenor": true,
        "treble": false,
        "book": {
            "id": 2,
            "title": "Book 2",
            "author": "Author 2",
            "date": "1990",
            "link": "www.book.com"
        }
    },
    {
        "id": 2,
        "side": "Right Side",
        "page_and_exercise": "pg. 12 Exercise 10",
        "tenor": true,
        "treble": false,
        "book": {
            "id": 3,
            "title": "Book 3",
            "author": "Author 3",
            "date": "1991",
            "link": "www.book2.com"
        }
    }
]
```

## Get the exercise info of an exercise
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
    "book": {
            "id": 2,
            "title": "Book 2",
            "author": "Author 2",
            "date": "1990",
            "link": "www.book.com"
    }
}
```

# Not implemented yet - TO DO

## Get a list of 50 exercises starting from num  - BENJAMIN
``` 
GET /api/exerciseinfo/start/<num>
```
Example response: /api/exerciseinfo/start/1
```
[
    {
        "id": 1,
        "side": "Left Side",
        "page_and_exercise": "pg. 11 Exercise 10",
        "tenor": true,
        "treble": false,
        "book": {
            "id": 2,
            "title": "Book 2",
            "author": "Author 2",
            "date": "1990",
            "link": "www.book.com"
        }
    },
    {
        "id": 2,
        "side": "Right Side",
        "page_and_exercise": "pg. 12 Exercise 10",
        "tenor": true,
        "treble": false,
        "book": {
            "id": 3,
            "title": "Book 3",
            "author": "Author 3",
            "date": "1991",
            "link": "www.book2.com"
        }
    },
    ...
]
```

## Get all exercises by author name / tag name - EREN
``` 
GET /api/exerciseinfo?filters={filters}
```
Parameters:
Name | Type | Mandatory |
------------ | ------------ |--|
author | STRING | NO | 
tag_id | INTEGER | NO
book_id | INTEGER | NO

Example response: /api/exerciseinfo?author=Mr. Author&tag_id=1&tag_id=2
```
[
    {
        "id": 1,
        "side": "Right side",
        "tenor": true,
        "treble": false,
        "page_and_exercise": "pg. 2 exercise 1"
        "book": {
                "id": 2,
                "title": "Book 2",
                "author": "Author 1",
                "date": "1990",
                "link": "www.book.com"
        }
    },
    {
        "id": 3,
        "side": "Right side",
        "tenor": true,
        "treble": false,
        "page_and_exercise": "pg. 2 exercise 1"
        "book": {
                "id": 5,
                "title": "Book 5",
                "author": "Author 1",
                "date": "1980",
                "link": "www.book5.com"
        }
    }
    ...
]
```


# Requires authentication (admin permissions) (implemented)
## Add a book to the table 
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

## Add a tag to the table 
```
POST /api/tag
```
Name | Type | Mandatory | Description
------------ | ------------ | ------------ | ------------
level | STRING | YES | Tag level (for now just 1, 2, or 3)
tag_name | STRING | YES |


## Add exercise information about a single exercise to the table 
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

## Add an exercise and its tag to the database 
```
POST /api/exercise
```
Name | Type | Mandatory | Description
------------ | ------------ | ------------ | ------------
exercise_id | INTEGER | YES | 
tag_id | INTEGER | YES
