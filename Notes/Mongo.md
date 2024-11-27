
# MongoDB: NoSQL Database
MongoDB is a document-based database, easy too use out of the box that comes with limitations.

Instead of tables, columns, and rows, it uses what's known as **collections** and **documents**.

Data in each document is stored as **field-value pairs** (BSON).

> Unlike Relational databases that use `SQL`, Here we use a language called `NoSQL`, meaning it's **not** a relational database.

## Benefits:
- It's much easier to work with this if you are used to something like JavaScript, because documents in MongoDB are very much like JSON or JS objects.
- Nested documents inside a document.
- High-speed performance.

### Key Terms:
- **Document**: A group of field-value pairs to represent an object.
- **Collection**: A group of one or more documents.
- **Database**: A group of one or more collections.

---

### Key Commands:

- `show dbs`  
  Lists available databases (won't show empty databases).

- `show collections`  
  Lists available collections in a database.

- `use [db-name]`  
  Uses the database. If no database with the name exists, it will create one.

- `db.createCollection("[name of the collection]")`  
  Adds a collection to a database.

- `db.dropDatabase()`  
  Drops the database.

- `db.[colc-name]`  
  Creates a collection in the current database with the given name if it doesn’t exist.

- `db.[colc-name].insertOne({field:value, ...})`  
  Inserts one document in the collection.

- `db.[colc-name].find()`  
  Returns the documents in a collection.

- `db.[colc-name].insertMany([{},{},...])`  
  Inserts multiple documents (array format).

## Data Types:

- **String**: `""` series of characters.
- **Integers**: Whole numbers.
- **Double**: Numbers with a decimal portion.
- **Booleans**: `true`/`false`.
- **Date Object**:  
  To create a date object: `new Date("")` (if no arguments are passed, it uses the current time in the UTC time zone).
- **Null**: No value.
- **Arrays**: `["", "", ...]`.
- **Nested Documents**: `{field:value, ...}`.


## Sorting and Limiting:

- `db.[colc-name].find().sort({[field-name]: 1/-1})`  
  Sorts the documents by the specified field. Use `1` for ascending and `-1` for descending.

- `db.[colc-name].find().limit([number])`  
  Limits the number of documents returned.

- `db.[colc-name].find().sort().limit()`  
  Sorts and limits the results.

## find()

- `find({field: value, ...})`  
  Finds and returns the documents where the field and value match.  
  ^Query parameter.

- `find({}, {field-name: true/false})`  
  Returns only the specified field(s) in the documents.  
  ^Projection parameter.

## Updating Documents:

- `db.[colc-name].updateOne({field: value}, {$set: {field: value}, $unset: {field: ""}})`  
  Updates one document.  
  ^Filter and Update.

- `db.[colc-name].updateMany({field: value}, {$set: {field: value}, $unset: {field: ""}})`  
  Updates multiple documents.


## Deleting Documents:

- `deleteOne()`  
  Deletes one document.

- `deleteMany()`  
  Deletes multiple documents.

Works similarly to the update commands.



## Comparison Operators:

- `[field-name]: { $ne: value }` --> Not equal.
- `[field-name]: { $lt: value }` --> Less than.
- `[field-name]: { $lte: value }` --> Less than or equal.
- `[field-name]: { $gt: value }` --> Greater than.
- `[field-name]: { $gte: value }` --> Greater than or equal.
- `[field-name]: { $in: ["", ""] }` --> Value inside an array.
- `[field-name]: { $nin: ["", ""] }` --> Value not inside the array.



## Logical Operators:

- `[field-name]: { $and: [{field: value}, {field: value}] }`
- `[field-name]: { $not: {field: value} }`
- `[field-name]: { $nor: [{field: value}, {field: value}] }`
- `[field-name]: { $or: [{field: value}, {field: value}] }`
