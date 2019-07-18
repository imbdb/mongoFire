# mongoFire
# Work in progress

## Example Usage
```
const MongoClient = require('mongodb').MongoClient;
const { mongoFire } = require('mongofire');
const url = 'mongodb://localhost:27017/';
const dbName = 'botdb';
var client, mdb, db;

async function handler(req, res) {
    try {
        client = await MongoClient.connect(url, { useNewUrlParser: true });
        mdb = client.db(dbName);
        db = new mongoFire(client, mdb);
        db.ref('flows').child(data.botID).child('responses').child(content).child('data').set({'test':'test'})
    } catch (e) { 
        console.log(e);
    }
}
```