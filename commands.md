# Show database:

show dbs;

# Create database;

use tungLeoDb;
db.getName();

# Create collections

db.createCollection("hello world");

# Delete database

db.dropDatabase();

# Collections (Same as table in SQL)

db.createCollection("person");
show collections
db.persion.stats()
db.person.drop()

# Documents (Like row in SQL)

## Use student collection

db.createCollection("student")

### or

student = {}

db.student.insert(student)

db.student.count

### Find

db.student.find().pretty()

## Insert many (Create)

db.student.insertMany(students)

## Find (Read)

db.student.find({})
db.student.find({firstName: 'Tung6'}).pretty()

### Only return the query field

db.student.find({firstName: 'Tung6'}, { firstName: 1 }).pretty()
db.student.find({firstName: 'Tung6'}, { firstName: 1, lastName: 1, gender: 1 }).pretty()

### Every single fields but firstName, lastName, gender

db.student.find({firstName: 'Tung6'}, { firstName: 0, lastName: 0, gender: 0 }).pretty()

## Update documents (Update)

### Set

db.student.update({\_id: ObjectId("615b2ed84a964fb1142a845a")}, {$set: {firstName: "LeoJr"}})

### Unset

db.student.update({\_id: ObjectId("615b2ed84a964fb1142a845a")}, {$unset: {lastName: 1}})

### Increment

db.student.find({}, { totalSpentInBooks: 1}).pretty()
db.student.update({\_id: ObjectId("615b2ed84a964fb1142a845a")}, {$inc: {totalSpentInBooks: 1}})

### Update an array

db.student.find({}, { favouriteSubjects: 1}).pretty()
db.student.update({\_id: ObjectId("615b2ed84a964fb1142a845a")}, {$pull: {favouriteSubjects: 'cs'}})

## Delete (Delete)

db.student.find({}, {\_id: 1}).pretty()
db.student.deleteOne({\_id: ObjectId("615b2d0d4a964fb1142a844f")})
