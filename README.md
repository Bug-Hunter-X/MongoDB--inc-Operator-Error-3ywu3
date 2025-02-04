# MongoDB $inc Operator Error
This example demonstrates an incorrect usage of the `$inc` operator in MongoDB. The `$inc` operator is used to increment a numerical field by a specified value. However, in this example, a string value is used, which causes an error.

## Bug
The bug lies in the following line of code:
```javascript
db.collection('myCollection').updateOne({"_id": 1}, {"$inc": {"count": "1"}});
```
The value passed to the `$inc` operator is a string (`"1"`) instead of a number (1).  This will result in a MongoDB error.

## Solution
The solution is to use a numerical value instead of a string value:
```javascript
db.collection('myCollection').updateOne({"_id": 1}, {"$inc": {"count": 1}});
```