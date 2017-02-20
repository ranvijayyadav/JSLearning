    **--Mongo DB--**
     
     MongoDb is nosql database
     
     NPM install mongodb 
     
     Require mongodb package 
        var mongodb = require('mongodb'); 
     configure url to connect
        var url ="mongodb://" + config.mongodb.host + ':' + config.mongodb.port + '/tableName';
     Create object of client 
        var client = mongodb.MongoClient;
     
     /Code snippet/
     /**
         var mongodb = require('mongodb');
         var configFile = (process.env.NODE_ENV ? process.env.NODE_ENV.toLowerCase() : 'local') + '.json';
         var config = require('./config/' + configFile);
         var url = "mongodb://" + config.mongodb.host + ':' + config.mongodb.port + '/history';
         var client = mongodb.MongoClient;
         var mongoDB;
         var db = client.connect(url, function(err, db) {
            if (err) {
                console.log("MongoDB ERROR>>>>>>" + err);
            } else {
                mongoDB = db;
            }
         });
         
         module.exports.get = function() {
            return mongoDB;
         };
     **/
     
     
     Connect  :
            Use client object to get access to DB instance
             var mongoDB;
             var db = client.connect(url, function(err, db) {
                if (err) {
                    console.log("MongoDB ERROR>>>>>>" + err);
                } else {
                    mongoDB = db;
                }
             });
     Store    :
     
     Use Instance of db to store data 
     var data={some data}
     mongoDB.get().collection('events').insert([data]);
     
     Retreive :
     Use Instance of db to Retreive data
     mongoDB.get().collection('events').collection.aggregate([query],callbackFunction);
     