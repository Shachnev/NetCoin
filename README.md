NetCoin (NTC)
===========

NetCoin (NTC)

## Linux
```
sudo apt-get install build-essential libboost-all-dev libcurl4-openssl-dev libdb5.3-dev libdb5.3++-dev git pyqt5-dev-tools libminiupnpc-dev zlib1g-dev libssl-dev
```

```
git clone https://github.com/netcoin/netcoin.git
cd netcoin/src
make -f makefile.unix USE_UPNP=- (or makefile.osx if you're on Mac OS)
```

Now I'm ready to run it–in testnet mode and with a connection to my “other” computer. This is kind of tricky, because you need to start the coin on both computers with the -connect=x.x.x.x variable, each with the IP of the other PC:
```
./netcoind -testnet -connect=x.x.x.x &
```

```
tail -f ~/.netcoin/testnet3/debug.log
```

Now's a good time to brush up on the command line API calls syntax for interacting with the bitcoin client from this wiki page: https://en.bitcoin.it/wiki/Original_Bitcoin_client/API_Calls_list
```
./netcoind getinfo
```
Lovely, they line up and each have a single connection. Now we can make one of them (or both) begin generating coins by using the following command:
```
./netcoind setgenerate true 16
```