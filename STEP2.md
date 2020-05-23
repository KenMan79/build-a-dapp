# What is Clusterpost?

[Clusterpost](https://github.com/juanprietob/clusterpost) is a grid computing tool that allows you to offload processes to a CouchDB database. However, for this SDK the migration is suggesting to use [BigChainDB](https://github.com/bigchaindb/bigchaindb/tree/tendermint-backward-compat) over CouchDB on the basis of decentralization opportunities. Clusterpost is also utilized for remotely scheduling and executing computational processes.

Here you can look at the code so:  
```
$ cd clusterpost
$ sudo ./setUpDevelopment.sh
$ sudo nano conf.production.json
```  
Let us start with looking at the following configs in the conf.production.json file  
```
{
    "host": "localhost",
    "port": 8180,
    "plugins": {
        "vision": {},
        "inert": {},
        "lout": {},
        "h2o2": {},
        "hapi-auth-jwt": {},
        "clusterpost-auth": {
            "privateKey": "someRandomKey",
            "saltRounds": 10,
            "algorithm": {
                "algorithm": "HS256"
            },
            "algorithms": {
                "algorithms": [ "HS256" ]
            },
```  
Here, you see the default port it should run on is 8180, you are welcome to change that if needed or open the port. Also you see the plugins or default NPM packages the production environment uses and the default algorithm for clusterpost’s authentication.

Next let us change the credentials as needed:  
```
},
            "mailer": {
                "nodemailer": "nodemailer-stub-transport",
                "from": "clusterpost server <insertemail@here.com>",
                "message": "Hello @USERNAME@,<br>Somebody asked me to send you a link to reset your password, hopefully it was you.<br>Follow this <a href='@SERVER@/public/#/login/reset?token=@TOKEN@'>link</a> to reset your password.<br>The link will expire in 30 minutes.<br>Bye."
            },
            "userdb" : {
                "hostname": "http://localhost:5984",
                "database": "clusterjobs"
            }
        },
```  
You need to setup the login either through nodemailer or the database program you are using and change the credentials so that clusterpost will be able to authenticate into the database.

Next while running the database you could run some tests, so:   
```
$ cd test
$ nautilus .
```  
You are free to look into the configs and test code as needed, but you can get started testing the default setup right away running: `npm run` or `node filename.js`

A good example would be  
```
$ cd test
$ node createNewJob.js
```
