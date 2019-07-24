# mongodb-auth


## 1. Go to admin 
use admin

## 2. Create User

db.createUser(
...   {
...     user: "test",
...     pwd: "*************",
...     roles: [ { role: "readWrite", db: "dbName" }, "readWriteAnyDatabase" ]
...   }
... )

##  3. For Creating user we need to create admin
  $db.auth("test","***********")

##  4.

db.createUser(
...   {
...     user: "test-local",
...     pwd: "***********",
...     roles: [ { role: "readWrite", db: "test" }, "readWriteAnyDatabase" ]
...   }
... )


##  5. mongorestore --host localhost:27017 -u test -p @************* --authenticationDatabase admin -d shenovi shenovi-needed

##  6. For dropping a db, We need to grant access

db.grantRolesToUser("test", ["root"]);

## 7.start mongo with auth
sudo mongod --auth --dbpath=/var/lib/mongodb2

