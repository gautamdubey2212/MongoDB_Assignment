use CRUD_DB
switched to db CRUD_DB
db["users"].find()
db.createCollection("users");
MongoServerError[NamespaceExists]: Collection already exists. NS: CRUD_DB.users
db.insertMany([{name:"Gautam"},])
TypeError: db.insertMany is not a function
db.users.insertMany([{name:"Gautam",
                     age: 25,
                     email:"gd@gmail.com",
                     country:"India"}]);
{
  acknowledged: true,
  insertedIds: {
    '0': ObjectId('6a15c3240bb23d304fe5d3e9')
  }
}
db.users.insertMany([{name:"Uttam",
                     age: 35,
                     email:"ut@gmail.com",
                     country:"India"}]);
{
  acknowledged: true,
  insertedIds: {
    '0': ObjectId('6a15c3350bb23d304fe5d3ea')
  }
}
db.users.insertMany([{name:"AGastya",
                     age: 45,
                     email:"At@gmail.com",
                     country:"India"}]);
{
  acknowledged: true,
  insertedIds: {
    '0': ObjectId('6a15c3490bb23d304fe5d3eb')
  }
}
db.users.find();
{
  _id: ObjectId('6a15c3240bb23d304fe5d3e9'),
  name: 'Gautam',
  age: 25,
  email: 'gd@gmail.com',
  country: 'India'
}
{
  _id: ObjectId('6a15c3350bb23d304fe5d3ea'),
  name: 'Uttam',
  age: 35,
  email: 'ut@gmail.com',
  country: 'India'
}
{
  _id: ObjectId('6a15c3490bb23d304fe5d3eb'),
  name: 'AGastya',
  age: 45,
  email: 'At@gmail.com',
  country: 'India'
}
db.users.find({age:{$gt:25$lt:35}});
SyntaxError: Identifier directly after number. (1:26)

> 1 | db.users.find({age:{$gt:25$lt:35}});
    |                           ^
db.users.find({age:{$gt:25,$lt:35}});
db.users.findOne({country:"India"});
{
  _id: ObjectId('6a15c3240bb23d304fe5d3e9'),
  name: 'Gautam',
  age: 25,
  email: 'gd@gmail.com',
  country: 'India'
}
db.users.update({name:"Gautam"},
                {set:danger@gmail.com});
SyntaxError: Unexpected token, expected "," (2:27)

  1 | db.users.update({name:"Gautam"},
> 2 |                 {set:danger@gmail.com});
    |                            ^
db.users.updateOne(
  { name: "Gautam" },
  { $set: { email: "danger@gmail.com" } }
);
{
  acknowledged: true,
  insertedId: null,
  matchedCount: 1,
  modifiedCount: 1,
  upsertedCount: 0
}
db.users.updateMany({age:{$gt:30}},
                    {$inc:{age:1}});
{
  acknowledged: true,
  insertedId: null,
  matchedCount: 2,
  modifiedCount: 2,
  upsertedCount: 0
}
db.users.deleteMany({country:"USA"});
{
  acknowledged: true,
  deletedCount: 0
}
db.users.delete();
TypeError: db.users.delete is not a function
db.users.deleteOne({name: "Gautam"});
{
  acknowledged: true,
  deletedCount: 1
}
-----------------------------------------------
----------------------------------------------
use Product_DB;
switched to db Product_DB
db.createCollection("products");
{ ok: 1 }
db.products.insertMany({name:"Rishika"})
MongoInvalidArgumentError: Argument "docs" must be an array of documents
db.products.insertMany({name:"iphone",
                       category:"Electronics",
                        price:$Rs2999,})
ReferenceError: $Rs2999 is not defined
db.products.insertMany({name:"iphone",
                       category:"Electronics",
                        price:$Rs2999,
                       quantity:"Large"});
ReferenceError: $Rs2999 is not defined
db.products.insertMany({name:"iphone",
                       category:"Electronics",
                        price:Rs2999,
                       quantity:"Large"});
ReferenceError: Rs2999 is not defined
db.products.insertMany({name:"iphone",
                       category:"Electronics",
                        price:2999,
                       quantity:"Large"});
MongoInvalidArgumentError: Argument "docs" must be an array of documents
db.products.insertMany([{name:"iphone",
                       category:"Electronics",
                        price:2999,
                       quantity:"Large"}]);
{
  acknowledged: true,
  insertedIds: {
    '0': ObjectId('6a15d7220bb23d304fe5d3ec')
  }
}
db.products.findMany();
TypeError: db.products.findMany is not a function
db.products.find();
{
  _id: ObjectId('6a15d7220bb23d304fe5d3ec'),
  name: 'iphone',
  category: 'Electronics',
  price: 2999,
  quantity: 'Large'
}
db.products.insertMany([{name:"Samsung",
                       category:"Electronics",
                        price:3999,
                       quantity:"Medium"}]);
{
  acknowledged: true,
  insertedIds: {
    '0': ObjectId('6a15d7ae0bb23d304fe5d3ed')
  }
}
db.products.insertMany([{name:"Car",
                       category:"AuoMobiles",
                        price:12,391,0099,
                       quantity:"Medium"}]);
SyntaxError: Unexpected token (3:36)

  1 | db.products.insertMany([{name:"Car",
  2 |                        category:"AuoMobiles",
> 3 |                         price:12,391,0099,
    |                                     ^
  4 |                        quantity:"Medium"}]);
db.products.find();
{
  _id: ObjectId('6a15d7220bb23d304fe5d3ec'),
  name: 'iphone',
  category: 'Electronics',
  price: 2999,
  quantity: 'Large'
}
{
  _id: ObjectId('6a15d7ae0bb23d304fe5d3ed'),
  name: 'Samsung',
  category: 'Electronics',
  price: 3999,
  quantity: 'Medium'
}
db.products.insertMany([{name:"Car",
                       category:"AuoMobiles",
                        price:123910099,
                       quantity:"Medium"}]);
{
  acknowledged: true,
  insertedIds: {
    '0': ObjectId('6a15d8190bb23d304fe5d3ee')
  }
}
db.products.find();
{
  _id: ObjectId('6a15d7220bb23d304fe5d3ec'),
  name: 'iphone',
  category: 'Electronics',
  price: 2999,
  quantity: 'Large'
}
{
  _id: ObjectId('6a15d7ae0bb23d304fe5d3ed'),
  name: 'Samsung',
  category: 'Electronics',
  price: 3999,
  quantity: 'Medium'
}
{
  _id: ObjectId('6a15d8190bb23d304fe5d3ee'),
  name: 'Car',
  category: 'AuoMobiles',
  price: 123910099,
  quantity: 'Medium'
}
db.products.find({price:{$gt:2000,$lt:100000000}});
{
  _id: ObjectId('6a15d7220bb23d304fe5d3ec'),
  name: 'iphone',
  category: 'Electronics',
  price: 2999,
  quantity: 'Large'
}
{
  _id: ObjectId('6a15d7ae0bb23d304fe5d3ed'),
  name: 'Samsung',
  category: 'Electronics',
  price: 3999,
  quantity: 'Medium'
}
db.products.findOne({category:"AuoMobiles"});
{
  _id: ObjectId('6a15d8190bb23d304fe5d3ee'),
  name: 'Car',
  category: 'AuoMobiles',
  price: 123910099,
  quantity: 'Medium'
}
db.products.updateOne({name:"car"},
                      {set:{category:"AutoMobiles GT"}});
MongoInvalidArgumentError: Update document requires atomic operators
db.products.updateOne({name:"car"},
                      {$set:{category:"AutoMobiles GT"}});
{
  acknowledged: true,
  insertedId: null,
  matchedCount: 0,
  modifiedCount: 0,
  upsertedCount: 0
}
db.products.findOne({category:"AutoMobiles GT"});
null
db.products.find();
{
  _id: ObjectId('6a15d7220bb23d304fe5d3ec'),
  name: 'iphone',
  category: 'Electronics',
  price: 2999,
  quantity: 'Large'
}
{
  _id: ObjectId('6a15d7ae0bb23d304fe5d3ed'),
  name: 'Samsung',
  category: 'Electronics',
  price: 3999,
  quantity: 'Medium'
}
{
  _id: ObjectId('6a15d8190bb23d304fe5d3ee'),
  name: 'Car',
  category: 'AuoMobiles',
  price: 123910099,
  quantity: 'Medium'
}
db.products.updateMany({quantity:{$lt:3000}},
                       {$dec:{quantity:100}});
MongoServerError: Unknown modifier: $dec. Expected a valid update modifier or pipeline-style update specified as an array
db.products.updateMany(
  { quantity: { $lt: 3000 } },
  { $inc: { quantity: -100 } }
);
{
  acknowledged: true,
  insertedId: null,
  matchedCount: 0,
  modifiedCount: 0,
  upsertedCount: 0
}
db.products.deleteMany({stock:0});
{
  acknowledged: true,
  deletedCount: 0
}
db.products.delete();
TypeError: db.products.delete is not a function
db.products.deleteOne({ name: "iphone" });
{
  acknowledged: true,
  deletedCount: 1
}
db.products.find();
{
  _id: ObjectId('6a15d7ae0bb23d304fe5d3ed'),
  name: 'Samsung',
  category: 'Electronics',
  price: 3999,
  quantity: 'Medium'
}
