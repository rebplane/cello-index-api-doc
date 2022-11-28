Out of date. This was only used for planning purposes.

Docs are now located here: https://cello-exercise-index.herokuapp.com/swagger/

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
Parameters:
Name | Type | Default | Description |
------------ | ------------ | --- | ---|
page | INTEGER | 1
page_size | INTEGER | 50 | The number of books requested (maximum 100)

Example response: /api/book?page=1
```
{
    "count": 31,
    "next": null,
    "previous": null,
    "results": [
        {
            "id": 1,
            "title": "Nouvelle Méthode de Violoncelle, Deuxième Partie *Part Two begins page 151",
            "author": "Abbiate, Louis",
            "date": "1900",
            "link": "https://imslp.org/wiki/Nouvelle_m%C3%A9thode_de_violoncelle_(Abbiate%2C_Louis)"
        },
        {
            "id": 2,
            "title": "La Technique du Violoncelle, Part Two, Gammes et Arpèges",
            "author": "Bazelaire, Paul",
            "date": "1925",
            "link": "https://imslp.org/wiki/La_Technique_du_Violoncelle_(Bazelaire%2C_Paul)"
        },
        ...
    ]
}
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
Parameters:
Name | Type | Default | Description |
------------ | ------------ | --- | --- |
page | INTEGER | 1
page_size | INTEGER | 50 | The number of tags requested (maximum 100)

Example response: /api/tag?page=1
```
{
    "count": 236,
    "next": "http://127.0.0.1:8000/api/tag/?page=2",
    "previous": null,
    "results": [
        {
            "id": 1,
            "level": 1,
            "tag_name": "Neck Positions Only"
        },
        {
            "id": 2,
            "level": 1,
            "tag_name": "Thumb Positions Only"
        },
        ...
    ]
}
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
Parameters:
Name | Type | Default | Description |
------------ | ------------ | --- | ---|
page | INTEGER | 1
page_size | INTEGER | 50 | The number of tags requested (maximum 100)

Example response: /api/tag/level/1?page=1
```
{
    "count": 39,
    "next": null,
    "previous": null,
    "results": [
        {
            "id": 1,
            "level": 1,
            "tag_name": "Neck Positions Only"
        },
        {
            "id": 2,
            "level": 1,
            "tag_name": "Thumb Positions Only"
        },
        ...
    ]
}
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
Parameters:
Name | Type | Default | Description | 
------------ | ------------ | ---| ---|
page | INTEGER | 1
page_size | INTEGER | 50 | The number of exercises requested (maximum 100)

Example response: /api/exerciseinfo?page=1
```
{
    "count": 1896,
    "next": "http://127.0.0.1:8000/api/exerciseinfo/?page=2",
    "previous": null,
    "results": [
        {
            "id": 1,
            "side": "Left Side",
            "page_and_exercise": "pp. 151–164",
            "tenor": false,
            "treble": false,
            "book_id": 1,
            "book": {
                "id": 1,
                "title": "Nouvelle Méthode de Violoncelle, Deuxième Partie *Part Two begins page 151",
                "author": "Abbiate, Louis",
                "date": "1900",
                "link": "https://imslp.org/wiki/Nouvelle_m%C3%A9thode_de_violoncelle_(Abbiate%2C_Louis)"
            }
        },
        ...
    ]
}
```

## Get a list of all exercises in a book
``` 
GET /api/exerciseinfo/book/<book_id>
```
Parameters:
Name | Type | Default | Description | 
------------ | ------------ | ---| ---|
page | INTEGER | 1
page_size | INTEGER | 50 | The number of exercises requested (maximum 100)

Example response: /api/exerciseinfo/book/2/?page=1
```
{
    "count": 65,
    "next": "http://127.0.0.1:8000/api/exerciseinfo/book/2/?page=2",
    "previous": null,
    "results": [
        {
            "id": 395,
            "side": "Left Side",
            "page_and_exercise": "pp. 4–16, Exercises 1–40",
            "tenor": false,
            "treble": false,
            "book_id": 2,
            "book": {
                "id": 2,
                "title": "La Technique du Violoncelle, Part Two, Gammes et Arpèges",
                "author": "Bazelaire, Paul",
                "date": "1925",
                "link": "https://imslp.org/wiki/La_Technique_du_Violoncelle_(Bazelaire%2C_Paul)"
            }
        },
        {
            "id": 527,
            "side": "Left Side",
            "page_and_exercise": "pp. 18–47, Scales and Arpeggios in all Major and Minor Keys",
            "tenor": false,
            "treble": true,
            "book_id": 2,
            "book": {
                "id": 2,
                "title": "La Technique du Violoncelle, Part Two, Gammes et Arpèges",
                "author": "Bazelaire, Paul",
                "date": "1925",
                "link": "https://imslp.org/wiki/La_Technique_du_Violoncelle_(Bazelaire%2C_Paul)"
            }
        }
    ]
}
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

## Get all exercises by author name / tag name / book - EREN
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
