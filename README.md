# MongoDB_basic
Workspace for Mongo DB basic

# Create Database
use mycustom

# Create User

db.createUser({
	user:"brad",
	pwd:"1234",
	roles:["readWrite","dbAdmin"]
});

> db.createCollection('customers')
{ "ok" : 1 }
> show collections
customers
> db.customers.insert({first_name:"John",last_name:"Doe")});
2017-08-09T01:52:49.241+0530 E QUERY    [thread1] SyntaxError: missing } after property list @(shell):1:54
> db.customers.insert({first_name:"John",last_name:"Doe"});
WriteResult({ "nInserted" : 1 })
> db.customers.find();
{ "_id" : ObjectId("598a1da2febb522c58b8fc6e"), "first_name" : "John", "last_name" : "Doe" }

> db.customers.insert([{first_name:"John",last_name:"Doe"},{first_name:"Rose",last_name:"Mary",gender:"female"}]);
BulkWriteResult({
        "writeErrors" : [ ],
        "writeConcernErrors" : [ ],
        "nInserted" : 2,
        "nUpserted" : 0,
        "nMatched" : 0,
        "nModified" : 0,
        "nRemoved" : 0,
        "upserted" : [ ]
})
> db.customers.find();
{ "_id" : ObjectId("598a1da2febb522c58b8fc6e"), "first_name" : "John", "last_name" : "Doe" }
{ "_id" : ObjectId("598a1ea7febb522c58b8fc6f"), "first_name" : "John", "last_name" : "Doe" }
{ "_id" : ObjectId("598a1ea7febb522c58b8fc70"), "first_name" : "Rose", "last_name" : "Mary", "gender" : "female" }
>

> db.customers.find().pretty();
{
        "_id" : ObjectId("598a1da2febb522c58b8fc6e"),
        "first_name" : "John",
        "last_name" : "Doe"
}
{
        "_id" : ObjectId("598a1ea7febb522c58b8fc6f"),
        "first_name" : "John",
        "last_name" : "Doe"
}
{
        "_id" : ObjectId("598a1ea7febb522c58b8fc70"),
        "first_name" : "Rose",
        "last_name" : "Mary",
        "gender" : "female"
}
