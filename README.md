# InstantFTP
> A Simple FTP server for sharing current folder with fast startup and multiconnection boosts for faster transmission.

## Introduction
`ftu` for Debian/Debian-Based and `ftw` Windows Operating Systems starts an FTP  server instantly on to the current folder of the sesison, happens all in you local network. 

These executables also print a `QR` on to the terminal for easy access of the ftp server link.

Automatically session logs are visible within the terminal logging who access which files and how many connections

![Demo usage of InstantFTP](https://raw.githubusercontent.com/devvratmiglani/InstantFTP/main/ftw-powershell-show.png)

⚠️ _**NOTE: These executables have anonymous user access too, don't use them in unsafe networks. You may consider recompiling with anonymous access removed and your own unique username:password**_ 

By the way you don't need to worry much if you are using it on home network 😛, still all devices in local network can access this link if they have this link (or if with credentials) or either they are scanning for open ports which is very uncommon, adding credentials adds a layer of security.

## Installation
To use them directly run the follwing command
```sh
git clone https://github.com/devvratmiglani/InstantFTP.git
```
and then set this directory in your PATHS or Environment variables
eg. '_C:\Tools\InstantFTP\\_' if you have git cloned in '_C:\Tools\\_' Directory.

## Usage
Launch a terminal and type 'ftu' or 'ftw' and the server insatntly starts sharing the curernt folder to all your devices in your local network.

## Recompiling
If you want to set a unique `username`:`password` for little more security I suggest to recompile the _`ft.py`_ using the belower `pyinstaller` command with made changes, you may need to run the following pyinstaller command first

```sh
pip install pyinstaller
``` 

These executables are compiled in respective environments using the pyinstaller as
```sh
pyinstaller .\ft.py --onefile --python-option u

```

## Multiple-Connection boost
These FTP server support 20 multiple connection per ip by default and can be increased in the _ft.py_ (isn't worth it though, 3-5 is more than enough) these can be beneficial when you are trying to download very large file over the network.

Can use multiple connections as 
```sh
aria2c -x16 -s16 ftp://user:pass@/host:port/path-to-file
```
Learn more [Aria2](https://github.com/aria2/aria2/)

For wired connections it will be extremely fast.
```
My stats:
Wired-Router-Wired: 527MBps
Wired-Router-Wireless: 60MBps
Wireless-Router-Wireless:  30MBps
(Transmission speed depends on your router too)
```




