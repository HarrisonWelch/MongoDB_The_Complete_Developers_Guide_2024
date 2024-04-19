# Time To Get Started!

```sh
test> show dbs
admin    40.00 KiB
config  108.00 KiB
local    72.00 KiB
```

### `use`

The use command will switch DB or create a new one if it doesn't already exist

```sh
test> use shop
switched to db shop
```

### Insertion

Using `insertOne` to insert one record into the DB

```sh
shop> db.products.insertOne({name: "A Book", price: 12.99})
{
  acknowledged: true,
  insertedId: ObjectId('6621e42e7a774b77f09f990a')
}
```

### `find`

Use `find` to find a specific record, or with no arg provided - return all records

```sh
shop> db.products.find()
[
  {
    _id: ObjectId('6621e42e7a774b77f09f990a'),
    name: 'A Book',
    price: 12.99
  }
]
```

#### pretty

`pretty()` will pretty print the records
* For some reason this is the same, maybe it was changed to the default as opposed to the instructor example in the video.

```
shop> db.products.find().pretty()
[
  {
    _id: ObjectId('6621e42e7a774b77f09f990a'),
    name: 'A Book',
    price: 12.99
  }
]
```

### Challenge to make an item with a Description

Self challenge to make an item with a description

```
shop> db.products.insertOne({name: "A T-Shirt", price: 12.99, "description": "This is a high quality T-Shirt"})
{
  acknowledged: true,
  insertedId: ObjectId('6621e54c7a774b77f09f990b')
}
```

And again lets pretty print

```
shop> db.products.find().pretty()
[
  {
    _id: ObjectId('6621e42e7a774b77f09f990a'),
    name: 'A Book',
    price: 12.99
  },
  {
    _id: ObjectId('6621e54c7a774b77f09f990b'),
    name: 'A T-Shirt',
    price: 12.99,
    description: 'This is a high quality T-Shirt'
  }
]
```

We see the **schemaless** part coming into play here

### Imbedded documents

Let's make a computer with details as an imbedded doc.

```sh
shop> db.products.insertOne({name: "A Computer", price: 12.99, description: "This is a high quality computer", details: {cpu: "Intel i7 8770", memory: 32}})
{
  acknowledged: true,
  insertedId: ObjectId('6621e64e7a774b77f09f990c')
}
```

```sh
shop> db.products.find().pretty()
[
  {
    _id: ObjectId('6621e42e7a774b77f09f990a'),
    name: 'A Book',
    price: 12.99
  },
  {
    _id: ObjectId('6621e54c7a774b77f09f990b'),
    name: 'A T-Shirt',
    price: 12.99,
    description: 'This is a high quality T-Shirt'
  },
  {
    _id: ObjectId('6621e64e7a774b77f09f990c'),
    name: 'A Computer',
    price: 12.99,
    description: 'This is a high quality computer',
    details: { cpu: 'Intel i7 8770', memory: 32 }
  }
]
```
