# White Raven

**This repo is a fork of [White Raven](https://github.com/silentmurdock/whiteraven) by Murdock. White Raven is a torrent player application for Samsung Smart TV E, F, H series. This repository contains the Smart TV Widget part of the application. The underlying server, which can be run on Windows, Linux, and rooted Samsung Smart TVs can be found in the [White Raven Server](https://github.com/nyakaspeter/White-Raven-Server) repository. To ease the assembly and deployment process the repo also includes a builder and an installer application.**

## Features

- Torrent server can run locally on rooted TV.
- Torrent streaming from memory.
- Automatic subtitle search by IMDB ID, Text or by File Hash.
- Torrent receiver page allow to stream any magnet link or torrent file.
- Favourites handler.
- Subtitle style settings.
- You can search for movies, episodes or whole season/series packs
- You can play torrents with multiple video files inside.

## Screenshots

![Screenshot](https://camo.githubusercontent.com/5685604ee5dc9b71d25c417e2b9eb4bdbce62292853616af1e1727ba68672db9/68747470733a2f2f692e6962622e636f2f7234673451346a2f747673686f77732e6a7067)

![Screenshot](https://camo.githubusercontent.com/ebcae33f28aa5d66416fd6642ed1111baeaafcd07c41ae2d89a75cd752267a69/68747470733a2f2f692e6962622e636f2f316e4e524374422f696e747673686f772e6a7067)

![Screenshot](https://camo.githubusercontent.com/b0cc589071750fd810e06467b31b9d3d15d152203993a2cb995469cfee6f3e4e/68747470733a2f2f692e6962622e636f2f6638624d5768362f747673686f777375627469746c652e6a7067)

![Screenshot](https://camo.githubusercontent.com/1515d18a46aeed1af351c1469c7b09da4838cb65d45438b0d2fe15a011277d61/68747470733a2f2f692e6962622e636f2f50574e5a7632432f6d6f766965732e6a7067)

![Screenshot](https://camo.githubusercontent.com/c96f920145ba15b4a248f0cad82c04aa55a4aafba6b5efc67ecd730c45225b47/68747470733a2f2f692e6962622e636f2f5a534c583243682f686f7374736d656e752e6a7067)

![Screenshot](https://camo.githubusercontent.com/8e4e07f5a3563f27b5259214be53fdefef5291460b8426d8404408fb5a6d1558/68747470733a2f2f692e6962622e636f2f32644c786a56662f696e646f776e6c6f6164322e6a7067)

![Screenshot](https://camo.githubusercontent.com/9331e8ded6b2914226f9da722cc2b9f7a7b07823468ae3cecd7953b786c61db3/68747470733a2f2f692e6962622e636f2f52516d764b51792f6d6f7669657375627469746c652e6a7067)

![Screenshot](https://camo.githubusercontent.com/3cc130756ebb28b2f934c412a28b98d5e59cb4f94760a6c4324e895a024231f9/68747470733a2f2f692e6962622e636f2f6e3150363350372f696e73657474696e67732e6a7067)

## How to use

### Running the server on the television

If you have a rooted E, F, or H series Samsung Smart TV, you can run both the client and the server simultaneously on your television.

1. [Download](https://github.com/nyakaspeter/whiteraven/releases) or [build](https://github.com/nyakaspeter/whiteraven#build-instructions) the root version of White Raven.
2. Connect to your television over FTP/SFTP.
3. Create a folder named as `WhiteRaven` (Case sensitive!) inside the `/mtd_rwcommon/widgets/user` directory.
4. Extract the contents of the downloaded zip file to this directory.
5. If you want to use the Jackett provider or tweak some server settings, modify `server.init` inside the `server` directory. See the [documentation](https://github.com/nyakaspeter/White-Raven-Server/blob/master/README.md) for possible launch arguments.
6. Reboot your television.
7. After reboot White Raven should show up in the apps section.
8. Start the White Raven widget and the server should start up automatically.

### Running the server on your local network

If you don't have root on your television or just don't want to run the server on the TV, you can also run it from another device on your local network.

0. [Download](https://github.com/nyakaspeter/White-Raven-Server/releases) or [build](https://github.com/nyakaspeter/White-Raven-Server#build-instructions) White Raven Server.
1. [Download](https://github.com/nyakaspeter/whiteraven/releases) or [build](https://github.com/nyakaspeter/whiteraven#build-instructions) the rootless version of White Raven.
2. Start up the server executable. If you want to use the Jackett provider or tweak some settings you must provide the necessary arguments. See the [documentation](https://github.com/nyakaspeter/White-Raven-Server/blob/master/README.md) for possible launch arguments.
3. Now you have 3 ways to get White Raven on your TV:
   - Run the widget from a USB stick:
      1. Grab a FAT32 formatted USB stick and create a folder named as `WhiteRaven` in it's root
      2. Extract the contents of the downloaded White Raven rootless zip file to this directory.
      3. Plug the pendrive into your television.
      4. White Raven should show up in the apps section. The pendrive has to be plugged in while using the app.
   - Use app sync to install White Raven:
      - I won't go into details here as this method removes all installed widgets from the television, but the instructions can be found [here](https://github.com/silentmurdock/whiteraven#install-with-application-synchronization).
   - If you have a rooted TV, you can also install the rootless version the same way as the root version. 
4. Start the White Raven widget and it should discover the server automatically.

## Build instructions

You can build the White Raven widget zip file by running the following commands from the project directory. [Go](https://golang.org/) must be installed for these to work.

### Building the rootless version

```
go run build.go rootless
```

### Building the rooted version

First you have to [download](https://github.com/nyakaspeter/White-Raven-Server/releases) or [build](https://github.com/nyakaspeter/White-Raven-Server#build-instructions) the server binary and place it in the project directory, then run:
```
go run build.go rooted -serverfile="wrserver"
```

## Donation
I don't ask for donations, but you can support the original creator for making this awesome app using these addresses:
```
BTC: 3NHNGcGEyD3m88nWZpNCSjnGq95rgFq4P5
LTC: MNyTkncUNkLgv8TCuPn69NVvBXnEsrtWcW
```
```
PATREON: https://www.patreon.com/murdock
```

## Terms Of Service
[TERMS OF SERVICE](TOS)

## License
[GNU GENERAL PUBLIC LICENSE Version 3](LICENSE)