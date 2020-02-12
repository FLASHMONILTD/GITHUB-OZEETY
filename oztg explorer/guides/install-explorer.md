--Block explorer pastes
```
sudo apt-get update
```
```
sudo apt install nodejs-legacy
```
```
sudo apt-get install npm
```
```
sudo apt-get install
```
Install Mongo DB
```
sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv EA312927
```
```
echo "deb http://repo.mongodb.org/apt/ubuntu xenial/mongodb-org/3.2 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-3.2.list
```
```
sudo apt-get update
```
```
sudo apt-get install -y mongodb-org
```
```
sudo systemctl start mongod
```
```
sudo npm install forever -g
```
Start mongodb cli: 
```
mongo
```
```
use explorerdb
```
```
db.createUser( { user: "diquidus", pwd: "dstra", roles: [ "readWrite" ] } )
```
```
exit
```
Install Explorer
```
git clone https://github.com/DSTRACoin/diquidus.git explorer
```
```
cd explorer && npm install --production
```
```
cp ./settings.json.template ./settings.json
```

To use forever to start (run in directory of explorer):
```
forever start bin/cluster
```
crontab information:
```
*/1 * * * * cd explorer && /usr/bin/nodejs scripts/sync.js index update > /dev/null 2>&1
```
```
*/5 * * * * cd explorer && /usr/bin/nodejs scripts/peers.js > /dev/null 2>&1
```
