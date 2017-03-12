## Quick Tutorial -Installing and running MongoDB and importing Json file on Mac OSX for newbies


```
brew update
brew install mongodb
```

This will install MongoDB in the following location:

/usr/local/var/Cellar/mongodb/

Double check if MongoDB is working by running the following command.
```
mongo -version
mongo -help
```

Create the database folder. MongoDB store data into the /data/db folder, you need to create this folder manually and assign proper permission.
```
$ sudo mkdir -p /data/db
$ whoami
(yourusername)
$ sudo chown (yourusername)/data/db```

Next add mongodb/bin to $PATH. You can use Vim or Nano (I hate VIM)

VIM:
```$ cd ~
$ pwd
/Users/agabardo
$ touch .bash_profile
$ vim .bash_profile```

OR

NANO:
```$ cd ~
$ pwd
/Users/agabardo
$ nano .bash_profile```

Add
```
export MONGO_PATH=/usr/local/mongodb
export PATH=$PATH:$MONGO_PATH/bin```

In another terminal window and start MongoDB with ```$ mongod```. (If it doesn't work try using ```$ sudo mongod```).

When you see the message: ‘waiting for connections on port 27017′ means that MongoDB is running. Next, open another terminal and type ```$ mongo```

#### Creating the database so we can import
Step 1: List Databases – First check the current databases in our system.

 ```# mongo
> show dbs; ```

You should see
 ```admin  (empty)
local  0.078GB
test   0.078GB```

## How to Create a New Mongodb Database
To create database with name "databasename", just run following command and save a single record in database. After saving your first example, you will see that new database has been created.

```> use databasename;```
```> s = { Name : "collection name" }```
```> db.testData.insert( s );```

Verify new database – 
Now if you list the databases, you will see the new database will be their with name databasename. Of course, in during a real project "databasename" would be the name of your actual database. Same for collection.

> show dbs;
admin  (empty)
local  0.078GB
databasename   0.078GB
test   0.078GB
```

## How to Import Json file into MongoDB database


"mongoimport --db databasename --collection collectioname --type json --file filenamejson --jsonArray

```

#DONE! 


## 2017 Credits
- Code: [Daitona Carter](http://daitonacarter.com/)
- Data: updating
- Illustration: updating
