Write code to:-

- create a database named sports.
  > use sports
- list all databases present in local mongod server.
  > show dbs
- create 3 collections named cricket, football, TT in sports databse.
  > sports> db.createCollection('cricket')
  > { ok: 1 }
  >
  > sports> db.createCollection('football')
  > { ok: 1 }
  >
  > sports> db.createCollection('TT')
  > {ok: 1}
- add multiple players in those collections which should have fields like name, age and email and bid_price.
  > db.cricket.insertMany([{name:'yatharth',age:23,email:'email2@gmail.com'},{name:'shubham',age:25,email:'email3@gmail.com'},{name:'sunny',age:20,email:'yatharthgiri187@gmail.com'}])
- list all collections in sports database.
  > db.sports.find()
- rename TT collection to tennis.
  > db.TT.renameCollection('tennis')
- create a capped collection called khokho which should have max 3 documents. Try inserting more than 3 and see what happens?
  > db.createCollection('khokho',{capped:true,size:2048,max:3})
- check whether a collection is capped or not?
  > db.khokho.isCapped()
- drop all documents from football collection.
  > db.football.drop({})
- delete cricket collection completely.
  > db.cricket.find()
- delete sports database.
  > db.dropDatabase()
- check which database you are connected to ?
  > db
- connect to test database
  > use test
