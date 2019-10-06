# Masternode Update 1005 
	

# LOGIN in your node via Putty! 

```bash
ozeety-cli stop
```
```bash
sudo wget https://github.com/thecoinmakers/ozeety-wallet-v1005/raw/master/Linux/ozeetyd
```
```bash
sudo wget https://github.com/thecoinmakers/ozeety-wallet-v1005/raw/master/Linux/ozeety-tx
```
```bash
sudo wget https://github.com/thecoinmakers/ozeety-wallet-v1005/raw/master/Linux/ozeety-cli
```
Permissions:
```bash
 chmod 777 *
```

```bash
sudo mv ozeetyd ozeety-cli ozeety-tx /usr/bin/
```
```bash
cd .ozeety
```
```bash
rm -R -f chainstate blocks .log mn.dat budget.dat peers.dat  mncache.dat mnpayments.dat fee_estimates.dat db.log debug.log database/ backups/ ozeety.pid .lock
```
Get chain 
```bash
sudo wget https://www.dropbox.com/s/fgca4r6oj35a0dj/chain-1005-2.zip
```
```bash
chmod 777 *
```
```bash
unzip chain-1005-2.zip
```

```bash
chmod 777 *
```

```bash
cd ~/
```
restart
```bash
ozeetyd 
```


to check if you are on the correct chain: 
on the wallet: in debug console type in: 
```bash
getblockhash 92740
```
Output should be: 
98ecbabc54aee33a10c09f60cdfd6fe75ddb13f376c30d4d5fbefe091b257141


to check for the correct chain on the node: 
check in putty as the user you setup the node: 
```bash
ozeety-cli getblockhash 92740
```
should be the same output:
98ecbabc54aee33a10c09f60cdfd6fe75ddb13f376c30d4d5fbefe091b257141
