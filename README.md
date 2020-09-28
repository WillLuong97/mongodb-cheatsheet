# MongoDB Cheat Sheets

All necessary and important MongoDB command lines that we must know in order to use MongoDB. 

## What is MongoDB? 

- MongoDB is a general purpose, document-based, distributed database built for modern application developers for the cloud. 

### The Document Model: 

- MongoDB is a document database, which means it stores data in JSON-like documens, as opposed to the table style or row/column document in MySql. This way, the data is much more expressive and object-oriented. 

- As a non-relational database schema, a document is stored as a big JSON blob with no particular format or schema. 




## Show all Databases: 

```
show dbs

```

## Show Current Database

```
db
```

## Create or Switch Database 

```
use dbName
```

## Drop or delete a Database: 

```
db.dropDatabase()
```

## Create Collections: 

```
db.createCollection('newCollections')
```

## Show Collections: 

```
show collections
```

## Insert Rows: 

```
db.posts.insert({
    title: 'Post One', 
    body: 'Body of post one'
    "_id" : ObjectId("5f6c107c001b332cdb27019b"),
    "title" : "Post One",
    "body" : "Body of Post One",
    "category" : "News",
    "tags" : [
        "news",
        "events"
    ],
    "user" : {
        "name" : "John Doe",
        "status" : "author"
    },
    "date" : "Wed Sep 23 2020 22:20:28 GMT-0500 (CDT)",
    "views" : 6
})
```

## Insert Multiple Rows

```
db.posts.insertMany([
{
    title: 'Post Two', 
    body: 'Body of post two',
    category: 'Technology',
    date: Date()
}, 

{
    title: 'Post Three',
    body: 'Body of post three',
    category: 'News',
    date: Date()

}, 

{
    title: 'Post Four',
    body: 'Body of Post Four',
    category: 'Entertainmenets',
    date: Date()
}
])
```

## Get All Rows: 

```
db.posts.find()
```

## Get all rows formatted: 

```
db.posts.find().pretty()
```

## Find rows: 

```
db.posts.find({category: 'News'})
```

## Sort Rows: 

```
#Ascending order: 
db.posts.find().sort({ title: 1}).pretty()

#Descending order: 
db.posts.find().sort({ title: -1 }).pretty()
```

## Count rows: 

```
db.posts.find().count()     # Count every rows in the chosen collections of the database
db.posts.find().({category: 'news' }).count     # Count the rows of a collection with a particular category
```


