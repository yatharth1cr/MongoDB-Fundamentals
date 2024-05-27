Write code to execute below mongoDB operations

### 1. Create a database named blog.

```
use blog
```

### 2. Create a collection called 'articles'.

```
db.createCollection("articles")
```

### 3 Insert multiple documents(at least 3) into articles. It should have fields

- title as string
- createdAt as date
- details as String
- author as nested object
  > - author should have
  >   > - name
  >   > - email
  >   > - age
  >   > - example author: {name: 'abc', email: 'abc@gmail', age: 25}
- tags : Array of strings like 'html', 'css'

```js
// An article should look like in the database
{
\_id: 'some_random_id',
title: '',
details: '',
author: {
name: '',
email: '',
age: ''
},
tags: ['js', 'mongo']
}
//
```

```js
db.articles.insertMany(threeDoc)
{
  acknowledged: true,
  insertedIds: {
    '0': ObjectId('66534b93a49fe511b1cdcdf6'),
    '1': ObjectId('66534b93a49fe511b1cdcdf7'),
    '2': ObjectId('66534b93a49fe511b1cdcdf8')
  }
}
```

### 4. Find all the articles using db.COLLECTION_NAME.find()

```js
-> db.articles.find()

//OUTPUT

[
  {
    _id: ObjectId('66534b93a49fe511b1cdcdf6'),
    title: 'title1',
    details: 'detail1',
    author: { name: 'name1', email: 'email1@gmail.com', age: '10' },
    tags: [ 'js', 'mongo' ]
  },
  {
    _id: ObjectId('66534b93a49fe511b1cdcdf7'),
    title: 'title2',
    details: 'detail2',
    author: { name: 'name2', email: 'email2@gmail.com', age: '20' },
    tags: [ 'js', 'mongo' ]
  },
  {
    _id: ObjectId('66534b93a49fe511b1cdcdf8'),
    title: 'title3',
    details: 'detail3',
    author: { name: 'name3', email: 'email3@gmail.com', age: '30' },
    tags: [ 'js', 'mongo' ]
  }
]
```

### 5. Find a document using \_id field.

```js
-> db.articles.findOne({_id: ObjectId('66534b93a49fe511b1cdcdf6')})

//OUTPUT
{
  _id: ObjectId('66534b93a49fe511b1cdcdf6'),
  title: 'title1',
  details: 'detail1',
  author: { name: 'name1', email: 'email1@gmail.com', age: '10' },
  tags: [ 'js', 'mongo' ]
}
```

### 6. Find documents using title

```js
-> db.articles.findOne({title:"title2"})

//OUTPUT

{
  _id: ObjectId('66534b93a49fe511b1cdcdf7'),
  title: 'title2',
  details: 'detail2',
  author: { name: 'name2', email: 'email2@gmail.com', age: '20' },
  tags: [ 'js', 'mongo' ]
}
```

### 7. Find documents using author's name field.

```
-> db.articles.findOne({"author.name":'name1'})

//OUTPUT

{
  _id: ObjectId('66534b93a49fe511b1cdcdf6'),
  title: 'title1',
  details: 'detail1',
  author: { name: 'name1', email: 'email1@gmail.com', age: '10' },
  tags: [ 'js', 'mongo' ]
}
```

### 8. Find document using a specific tag.

```
-> db.articles.findOne({tags:['js','mongo']})

//OUTPUT

{
  _id: ObjectId('66534b93a49fe511b1cdcdf6'),
  title: 'title1',
  details: 'detail1',
  author: { name: 'name1', email: 'email1@gmail.com', age: '10' },
  tags: [ 'js', 'mongo' ]
}
```

### 9. Update title of a document using its \_id field.

```js
-> db.articles.update({_id: ObjectId('66534b93a49fe511b1cdcdf8')},{$set:{title:"updatedTitle"}})

//OUTPUT

DeprecationWarning: Collection.update() is deprecated. Use updateOne, updateMany, or bulkWrite.
{
  acknowledged: true,
  insertedId: null,
  matchedCount: 1,
  modifiedCount: 1,
  upsertedCount: 0
}
```

### 10. Update a author's name using article's title.

```js
blog> db.articles.update({title:"title1"},{$set:{"author.name":"updatedName"}})
//OUTPUT
{
  acknowledged: true,
  insertedId: null,
  matchedCount: 1,
  modifiedCount: 1,
  upsertedCount: 0
}
```

### 11. Rename details field to description from all articles in articles collection.

### 12. Add additional tag in a specific document.

### 13. Update an article's title using $set and without $set.

- Write the differences here ?

### 14. find an article using title and increment author's age by 5.

### 15. Delete a document using \_id field with db.COLLECTION_NAME.remove().

// Sample data

```js
db.users.insertMany([
  {
    age: 49,
    name: "Maurice Brock",
    email: "wuk@hibpiz.ch",
    gender: "Female",
    sports: ["cricket", "football"],
    scores: [24, 35, 18, 16],
    weight: 45,
  },
  {
    age: 37,
    birthday: "7/15/1986",
    name: "Virgie Cunningham",
    email: "ezogafa@de.gm",
    gender: "Male",
    sports: ["football"],
    scores: [17, 35, 43],
    weight: 52,
  },
  {
    age: 48,
    birthday: "5/14/1961",
    name: "Alexander Holt",
    email: "han@mu.pe",
    gender: "Male",
    sports: ["cricket", "football", "TT"],
    scores: [24, 30, 16],
    weight: 55,
  },
  {
    age: 53,
    birthday: "11/15/1963",
    name: "Derek Dawson",
    email: "polril@now.de",
    gender: "Male",
    sports: ["cricket", "hockey"],
    scores: [20, 15, 38, 23],
    weight: 49,
  },
  {
    age: 34,
    birthday: "7/24/1964",
    name: "Cynthia Cobb",
    email: "wujjarpob@jecimpar.gu",
    gender: "Female",
    sports: ["cricket"],
    scores: [41, 17, 28],
    weight: 51,
  },
  {
    age: 33,
    birthday: "10/26/1982",
    name: "Isabella Atkins",
    email: "ononuzas@givhoz.ca",
    gender: "Female",
    sports: ["cricket", "football", "hockey", "TT"],
    scores: [14, 38, 29, 45, 20],
    weight: 49,
  },
  {
    age: 47,
    birthday: "10/12/1978",
    name: "Katharine Bryan",
    email: "zo@pebi.sa",
    gender: "Male",
    sports: ["TT", "hockey", "khokho"],
    scores: [27, 20, 34],
    weight: 58,
  },
  {
    age: 41,
    birthday: "1/28/1991",
    name: "Beatrice Fleming",
    email: "ufufsa@pujizren.tk",
    gender: "Female",
    sports: ["football", "khokho"],
    scores: [30, 20, 15, 29, 43],
    weight: 47,
  },
  {
    age: 26,
    birthday: "3/23/1998",
    name: "Tom Fields",
    email: "wasodjow@ofaba.gf",
    gender: "Female",
    sports: ["khokho"],
    scores: [37, 29, 18, 43, 49],
    weight: 50,
  },
  {
    age: 33,
    birthday: "11/14/1960",
    name: "Steve Ortega",
    email: "dupus@ca.ls",
    gender: "Female",
    sports: ["cricket", "football", "hockey"],
    scores: [12, 15, 20],
    weight: 51,
  },
  {
    age: 24,
    birthday: "1/5/1994",
    name: "Suraj Kumar",
    weight: 50,
    gender: "Male",
    sports: ["football", "cricket", "TT"],
  },
]);
```

Insert above data into database to perform below queries:-

Find all males who play cricket.
Update user with extra golf field in sports array whose name is "Steve Ortega".
Find all users who play either 'football' or 'cricket'.
Find all users whose name includes 'ri' in their name.
