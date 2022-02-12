view all databases

- `show dbs`

create a new db or use an existing db

- `use dbName`

view current db

- `db`

delete database

- `db.dropDatabase()`

show collections within the db

- `show collections`

create a new collection

- `db.createCollection('collection_name')`

delete a collection

- `db.collection_name.drop()`

insert a row in a collection

```
db.collection_name.insert(
                          {
                           "name": "Souvik Guria",
                           "dept": "MCA",
                           "langs": "Python, Javascript, dart"
                          })
```

insert many rows in a collection / insert multi docs in a collection

- eg:

```
    db.collection_name.insertMany([
                                 {"name": "Souvik Guria", "dept": "MCA", "langs": "Python, Javascript, dart"},
                                 {"name": "Rahul", "dept": "MCA", "langs": "C++, Java"},
                                 {"name": "Mohit", "dept": "B.Tech", "langs": "C, Python"}
                                ])
```

show all rows in a collection

- `db.collection_name.find()`

to format and display

- `db.collection_name.find().pretty()`

search an obj in the db

- `db.collection_name.find({condition1, condition2}).pretty()`
- ex: `db.one.find({"name": "Rahul", "lang": "C++, Java"})`

view only n nums of objs

- `db.collection_name.find().pretty().limit(n)`

count the no of docs in a collection

- `db.collection_name.find().count()`

count the no of rows printed

- `db.collection_name.find().limit(2).count()`

Find the first row matching the object

- `db.collection_name.findOne(condition)`

update a row (Note: include all the fields, even in inserted before, else they will get deleted)

- `db.one.update({search filter}, {data field to be updated})`
  eg:

```
db.one.update({"name": "Rohit"},
              {
              "name": "Rohit",
              "dept": "MCA",
              "langs": "C, C++, Python",
              "member_since": 5
              })
```

update new row and also insert if not existing

- eg:

```db.one.update({"name": "Rohit"},
                {
                "name": "Rohit",
                "dept": "MCA",
                "langs": "C, C++, Python",
                "member_since": 3
                },
                {upsert: true})
```

sort by a col name

- `db.one.find().sort({member_since: 1}).pretty()`
  `1 means ascending order, -1 means descending order`

delete a row:

- `db.collection_name.remove({condition})`

#### operators in mongoDB

[here](https://www.bmc.com/blogs/mongodb-operators/)
