ꝄibweeCoin (KiB)
================

https://www.kibwee.com

Copyright (c) 2009-2013 Bitcoin Developers
Copyright (c) 2011-2014 DarkCoin Developers
Copyright (c) 2014 KibweeCoin Developers


What is KibweeCoin?
-------------------

KibweeCoin is a lite version of Bitcoin using X11 as a proof-of-work algorithm.
 - GPU/CPU only mining
 - Block generation: 1 minutes
 - Difficulty Retargets every block using DGW
 - Est. ~3.7M Coins

KibweeCoin is also simulating mining for the non miners through a proof-of-contribution concept.
To participate to the PoC, please visit our website.

For more information, see https://www.kibwee.com


License
-------

KibweeCoin is released under the terms of the MIT license. See `COPYING` for more
information or see http://opensource.org/licenses/MIT.


Social Network
--------------

Website / PoC Console: https://www.kibwee.com
Twitter: @kibweecoin
Facebook: https://www.facebook.com/profile.php?id=100005694165617
BTCTalk: https://bitcointalk.org/index.php?topic=642933.0
IRC Freenode: #kibwee


Specifications
--------------

Monetary symbol:
Ꝅ
Unicode number: U+A744
HTML-code: &#42820;

PoW Algorithm: X11
PoC Algorithm: None
PoS Interest: 2% / year

PoW Basic reward per block: 8 KiB
PoW Time target per block: 60 seconds
PoW Distribution: The block finder earn the reward
PoW Difficulty adjustment: Dark Gravity Well
PoW Reward halves: on block 43200 (4 from 8 ), 129600 (2 from 4) and 259200 (1 from 2)
PoW coins to be mined: 1.019.520 KiB

PoC Time target per Roll: every 60 blocks (60 minutes)
PoC basic reward: 472 KiB
PoC Distribution: shared between all Contributors
PoC total coins: 2.718.720 KiB

PoW + PoC total coins: 3.738.240 KiB
PoW/PoC Block maturity: 220 blocks
End of the PoW/PoC period: on block 345600 (target: 8 months)
 
Transaction confirmations: 6


Config file example (kibweecoin.conf)
-------------------------------------

rpcuser=kibuser
rpcpassword=kibpass
port=38000
rpcport=38001
maxconnections=200
rpcallowip=localhost
rpcconnect=localhost
gen=0
testnet=0
addnode=37.187.193.228


Linux Compilation
-----------------

Main Dependencies:

sudo apt-get install -y build-essential libssl-dev libdb-dev libdb++-dev libboost-all-dev libqrencode-dev libcurl4-openssl-dev
wget http://miniupnp.free.fr/files/download.php?file=miniupnpc-1.8.tar.gz && tar -zxf download.php\?file\=miniupnpc-1.8.tar.gz && cd miniupnpc-1.8/
sudo make && sudo make install && cd .. && rm -rf miniupnpc-1.8 download.php\?file\=miniupnpc-1.8.tar.gz

Daemon:

cd kibweecoin/src/leveldb/
sh build_detect_platform build_config.mk ./
cd ..
make -f makefile.unix
strip kibweecoind

QT:
cd kibweecoin/
qmake-qt4
make
