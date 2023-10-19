# White Raven

White Raven is a torrent player application for Samsung Smart TV E, F, H series. This repository contains the Smart TV Widget part of the application. For it to work, the [Raven Server](https://github.com/nyakaspeter/Raven-Torrent) application must also be running on the TV (which is only possible if it's rooted), or on the local network. I recommend setting up a [Jackett](https://github.com/Jackett/Jackett) server too, to get the most out of the application. This repo is a fork of [White Raven](https://github.com/silentmurdock/whiteraven).

## Features

- Torrent server can run locally on rooted TV
- Torrent streaming from memory
- Automatic subtitle search by IMDB ID, Text or by File Hash
- Torrent receiver page allow to stream any magnet link or torrent file
- Favourites handler
- Subtitle style settings
- You can search for movies, episodes or whole season/series packs
- You can play torrents with multiple video files inside

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

### Rootless version

If you don't have root on your television or just don't want to run the server on the TV, you can also run it from another device on your local network. For this you have to [download](https://github.com/nyakaspeter/White-Raven/releases) the rootless version of White Raven and run [Raven Server](https://github.com/nyakaspeter/Raven-Torrent/releases) separately. I also recommend setting up a [Jackett](https://github.com/Jackett/Jackett) server on your local network, to be able to use a significantly higher number of torrent trackers. Instructions for running Raven Server and Jackett on various devices can be found [here](https://github.com/nyakaspeter/Raven-Torrent#how-to-use).

#### Running the widget from USB on Samsung Smart TV E, F, H series

0. Ensure that Raven Server is running on the local network.
1. Grab a FAT32 formatted USB stick and create a folder named as `WhiteRaven` in it's root.
2. Extract the contents of the downloaded White Raven rootless zip file to this directory.
3. Plug the pendrive into your television.
4. White Raven should show up in the apps section. After launching it, it should automatically connect to the server. The pendrive has to be plugged in while using the app.

#### Installing the widget on rooted Samsung Smart TV E, F, H series</summary>

0. Ensure that Raven Server is running on the local network.
1. Connect to your television over FTP/SFTP.
2. Create a folder named as `WhiteRaven` inside the `/mtd_rwcommon/widgets/user` directory.
3. Extract the contents of the downloaded zip file to this directory.
4. Reboot your television.
5. After reboot White Raven should show up in the apps section. After launching it, it should automatically connect to the server.

### Root version

If you have a rooted E, F, or H series Samsung Smart TV, you can run both the client and the server simultaneously on your television. For this you have to [download](https://github.com/nyakaspeter/White-Raven/releases) the root version of White Raven. I also recommend setting up a [Jackett](https://github.com/Jackett/Jackett) server on your local network, to be able to use a significantly higher number of torrent trackers. Unfortunately Jackett cannot be run from the TV itself, but it can run on a number of devices, I've written about it [here](https://github.com/nyakaspeter/Raven-Torrent#how-to-use).

#### Installing the widget on rooted Samsung Smart TV E, F, H series

1. Connect to your television over FTP/SFTP.
2. Create a folder named as `WhiteRaven` inside the `/mtd_rwcommon/widgets/user` directory.
3. Extract the contents of the downloaded zip file to this directory.
4. If you want to use the Jackett provider or tweak server settings, modify `server.init` inside the `server` directory. See the [documentation](https://github.com/nyakaspeter/Raven-Torrent#cli-arguments) for launch arguments.
5. Reboot your television.
6. After reboot White Raven should show up in the apps section. After launching it, it should automatically start the server and connect to it.

## Build instructions

You can build the White Raven widget zip file by running the following commands from the project directory. [Go](https://golang.org/) must be installed for these to work.

#### Building the rootless version

`go run build/build.go rootless`

#### Building the rooted version

First you have to [download](https://github.com/nyakaspeter/Raven-Torrent/releases) or [build](https://github.com/nyakaspeter/Raven-Torrent#build-instructions) the ARM version of the server binary and place it in the `build` directory, then run:

`go run build/build.go rooted -serverfile="build/raven"`

## Terms of service
[TERMS OF SERVICE](TOS)

## License
[GNU GENERAL PUBLIC LICENSE Version 3](LICENSE)
