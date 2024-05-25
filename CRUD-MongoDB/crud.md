Write code to:-

## 1. create a database named mountains

- > use mountains

## 2. a collection inside that database named himalayas

- > db.createCollection('himalayas)

## 3. insert 1 document into that collection {name: 'Dhauldhar range', height: '4000 mtrs'}

- > db.himalayas.insert({name: 'Dhauldhar range', height: '4000 mtrs'})

## 4. insert multiple document using insertMany command

```
 mountains> db.himalayas.insertMany([{name: 'Dhauldhar range', height: '4000 mtrs'},{name: 'mountain2', height: '1300 mtrs'},{name: 'mountain3', height: '6000 mtrs'}])
 {
 acknowledged: true,
 insertedIds: {
    '0': ObjectId('6650ea70477a58cb71cdcdf7'),
    '1': ObjectId('6650ea70477a58cb71cdcdf8'),
    '2': ObjectId('6650ea70477a58cb71cdcdf9')
 }
 }
```

## 5. find all documents from mountains

- > db.himalayas.find()

## 6. find a single document using name

```
-> db.himalayas.findOne({name:'mountain2'})
{
_id: ObjectId('6650ea70477a58cb71cdcdf8'),
name: 'mountain2',
height: '1300 mtrs'
}
```
