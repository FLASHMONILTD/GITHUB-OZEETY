## Explorer guide
## ===============

### install required nodejs ver. v6 on 16.04, v8 on 18.04 ubuntu

* sudo apt-get update
* sudo curl -sL https://deb.nodesource.com/setup_6.x | sudo -E bash -
* sudo apt-get install -y nodejs
* sudo npm install
* sudo apt-get install


## Install Mongo DB
## ================

* sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv EA312927
* echo "deb http://repo.mongodb.org/apt/ubuntu xenial/mongodb-org/3.2 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-3.2.list
* sudo apt-get update
* sudo apt-get install -y mongodb-org
* sudo systemctl start mongod
* sudo npm install forever -g


## Start mongodb cli:
## =================

#db.createUser( { user: "iquidus", pwd: "3xp!0reR", roles: [ "readWrite" ] } )
#old iquidus

mongo

* use explorerdb
* db.createUser( { user: "diquidus", pwd: "dstra", roles: [ "readWrite" ] } )
* exit


## Install Explorer
## ================

* git clone https://github.com/DSTRACoin/diquidus.git explorer

* cd explorer && npm install --production

* cp ./settings.json.template ./settings.json

### To use forever to start (run in directory of explorer):

forever start bin/cluster

### Start reindexing the blocks

node scripts/sync.js index reindex

crontab -e

crontab information:
#*/2 * * * * cd /root/explorer && /usr/bin/nodejs scripts/sync.js market > /dev/null 2>&1

```
*/1 * * * * cd /root/explorer && /usr/bin/nodejs scripts/sync.js index update > /dev/null 2>&1
*/2 * * * * cd /root/explorer && /usr/bin/nodejs scripts/masternodes.js > /dev/null 2>&1
*/5 * * * * cd /root/explorer && /usr/bin/nodejs scripts/peers.js > /dev/null 2>&1
```
