## Write command to

##### 1. List collections from a database.

> show collections

##### 2. create a new collection in your country database which you created recently.

> show dbs
> db.createCollection("state")

## Write code to:-

##### 1. create a database named weather

> use weather

##### 2. create a capped collection named temperature with maximum of 3 documents and try inserting more than 3 to see the result.

> db.createCollection("temperature",{capped:true,size:2020,max:3})

##### 3. create a simple collection named humidity

> db.createCollection("humidity")

##### 4. check whether temperature collection is capped or not ?

> db.temperature.isCapped() //true
> db.humidity.isCapped() //false

##### 5. Delete humidity collection and then the entire database(weather).

> db.humidity.drop()
>
> db.dropDatabase()
