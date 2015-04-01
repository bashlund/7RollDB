#7RollDB - The Non Bloated Database
A MongoDB replacement written in Bash.

A novel database engine for courageous users.

##Features of 7RollDB
* Free and open source
* JSON document database engine
* Strict Non Bloating Policy
* Super lightweight - only ~5kb in size
* Built in REST API
* Written in Bash - the super popular shell language supported everywhere
* Unlimited scalability -
    * Connect 7RollDB to your Dropbox and enjoy limitless scalability for life
* MongoDB port compatible (uses 27017)
* Growing community

##Non Bloating policy
While MongoDB started out as a sleek shut-the-fcuk-up database engine, it has now
more or less conformed to traditional database technologies.

It used to be super lean without transaction logs or even write confirmations,
but somewhere along the line of playing with the big boys n' girls, they completely lost the ball and their ways of NoSQL.

7RollDB is filling that vacuum for a novel database engine and its courageous users.

7RollDB adhere to our strict Non Bloating Policy of never getting bloated on the users expense.


##Comparing 7RollDB to MongoDB*
                | 7RollDB   | MongoDB
    ----------- | --------- | -------------
    Non Bloating Policy     | Strict      | None
    Sleak       | Yes      | No
    Bash        | Yes      | No
    REST API    | Native      | No (depends on 3rd party)
    RAM friendly   | Yes | No (uses memory mapped files)
    Performant  | Yes      | Yes
    Scalable    | Yes      | Yes

\* I have never actually used MongoDB

##HTTP REST API
7RollDB comes with a fully featured expandable REST API to handle your JSON documents.

###Databases
Create new database:
```sh
$ curl -X POST "http://127.0.0.1:27017/MyDB1"
{status: "OK"}
```
List all databases:
```sh
$ curl -X GET "http://127.0.0.1:27017/"
[
    "MyDB1"
]
```

###Collections
Create new collection within database:
```sh
$ curl -X POST "http://127.0.0.1:27017/MyDB1/MyCollection1"
{status: "OK"}
```
List all collections withinin specific database:
```sh
$ curl -X GET "http://127.0.0.1:27017/MyDB1"
[
    "MyCollection1"
]
```
###Documents
Create new or update a document within a collection:
```sh
$ curl -X POST "http://127.0.0.1:27017/MyDB1/MyCollection1/OhSoSweetDocument" -d \
        '{"name": "Alexander McRaminov", "occupation": "Plain Cool"}'
{status: "OK"}
```
List all documents within specific collection:
```sh
$ curl -X GET "http://127.0.0.1:27017/MyDB1/MyCollection1"
[
    "OhSoSweetDocument"
]
```
Get a specific document:
```sh
$ curl -X GET "http://127.0.0.1:27017/MyDB1/MyCollection1/OhSoSweetDocument"
{"name": "Alexander McRaminov", "occupation": "Plain Cool"}

```
Delete a specific document:
```sh
$ curl -X DELETE "http://127.0.0.1:27017/MyDB1/MyCollection1/OhSoSweetDocument"
{status: "OK"}
```

###Query and search
7RollDB uses a very down to earth and proved technique for searching through documents
while still never sidestepping our strict 0 relations and 0 indexing Non Bloating Policy.

Searching for documents in all collections within a database:
```sh
$ curl -X GET "http://127.0.0.1:27017/MyDB1?Alexander"
[
    "MyCollection1/OhSoSweetDocument"
]
```
Searching for documents within a specific collection:
```sh
$ curl -X GET "http://127.0.0.1:27017/MyDB1/MyCollection1?McRaminov"
[
    "OhSoSweetDocument"
]
```
Searching within a specific document for a match:
```sh
$ curl -X GET "http://127.0.0.1:27017/MyDB1/MyCollection1/OhSoSweetDocument?Cool"
[
    "OhSoSweetDocument"
]
```

##Installation
7RollDB depends on some GNU utils and *socat*. Socat is like Netcat++.
```sh
$ sudo apt-get install socat
or
$ sudo pacman -S socat
or
$ brew install socat
```
Clone the 7RollDB repo:
```sh
$ git clone https://github.com/thomasbacklund/7rolldb.git
cd 7rolldb
./7rolldb
```
See `curl` examples above for how to connect to 7RollDB.

All `database storage` is within the `./data/` directory.

##Contribute
Contributions are welcome.
There is still room for improvement within our strict Non Bloating Policy.

##Disclaimer
You will be using 7RollDB at your own risk.

##Contact
Get in touch with @ThomasBacklund on Twitter

##Donate
You could support the further development of 7RollDB by donating some bitcoins.

All donations will be used in coherence with our strict Non Bloating Policy.

Bitcoin address: `17RoLLNFzN24CJCdbRNdA5pJqAWzRzXsze`
