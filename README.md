# pokerth
PokerTH is a poker game written in C++/Qt.
see orignal project: [pokerth](https://github.com/pokerth/pokerth)

This is a really fast and very nice Texas Hold'em Poker implementation!!!

In this repro I updated the sources made them compile on Ubuntu 18.04.6 LTS Bionic Beaver.
1st I merged the new_local_game branch into stable and build the executeable.
My main goal is to look into the AI behind the client and play around with it.
To get a kind of poker trainer I'm planning to add an option for PeekMode.

## Ubuntu 18.04.6 LTS Remarks - Client QT 5, with boost 1.62/1.65
Install DEVELOPMENT packages for client:

sudo apt install git
sudo apt install qtbase5-dev qtchooser qt5-qmake qtbase5-dev-tools
sudo apt install zlib1g-dev
sudo apt install libcurl4-gnutls-dev
sudo apt install libboost-all-dev
	a bit of an overkill...
sudo apt install libtinyxml-dev
sudo apt install libsdl-mixer1.2-dev libsdl1.2-dev
sudo apt install libsqlite3-dev
sudo apt install libgsasl7-dev 
sudo apt install libprotobuf-dev
sudo apt install protobuf-compiler
sudo apt install g++-6
sudo apt install libgcrypt20-dev

I choosed to use GCC 6.x instead of default 7.x (to be tested...)

qmake, also see [wiki](https://github.com/pokerth/pokerth/wiki/Building-PokerTH-for-Linux) with following options:
```
$ /usr/lib/x86_64-linux-gnu/qt5/bin/qmake CONFIG+="client c++11 debug" QMAKE_CC="/usr/bin/gcc-6" QMAKE_CXX="/usr/bin/g++-6" QMAKE_CFLAGS_ISYSTEM="" -spec linux-g++ pokerth.pro
```
maybe remove debug from CONFIG+, but it may be helpfull with gdb...
