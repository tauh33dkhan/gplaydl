## Command Line Utility to Download APK Files
Download APK files from Google Play Store to your PC directly. A command line implementation of [NoMore201/googleplay-api](https://github.com/NoMore201/googleplay-api/)

## Web-based APK Downloader
I've launched an awesome <a href="https://apktools.io/online-apk-downloader/">web-based APK downloader here</a> that you can use to download APK files to your PC directly from Google Play Store. It supports split APKs as well and the download links from Google servers are directly served to you.

### Installation
`pip3 install gplaydl`

or

`git clone https://github.com/rehmatworks/gplaydl.git`

CD into `gplaydl` and then:

`python3 setup.py install`

### Usage:
```bash
-h, --help            show this help message and exit
-c, --configure       Create the configuration file by providing your Google
                     email and password (preferably app password).
-id, --packageId
                     Package ID of the app, i.e. com.whatsapp
-e, --email
                     Google username
-p, --password
                     Google password
-d, --directory
                     Path where to store downloaded files
-dc, --deviceCode
                     Device code name
-ex, --expansionfiles
                     Download expansion (OBB) data if available
```

### Examples
Save your email and password in config cache:
```
gplaydl --configure -e email@gmail.com -p passwordOrAppPassword
```
Download an APK file (i.e. WhatsApp):
```
gplaydl -id com.whatsapp
```

Use `gplaydl` without saving login info in cache:
```
gplaydl -id com.whatsapp -e email@gmail.com -p password
```

Store APK file in a custom directory:
```
gplaydl -id com.whatsapp -d folder-name-or-path
```

Download a game with expansion (OBB) files (Does not make a difference if expansion files are not available for an app or a game):
```
gplaydl -id com.rayark.Cytus.full -ex
```

Upload a specific device by code (Defaults to `bacon`) ([Available Devices](https://github.com/NoMore201/googleplay-api/blob/master/gpapi/device.properties)):

```
gplaydl -id com.whatsapp -dc angler
```

### Features:
* No need to provide device ID (Generated automatically))
* No need to provide auth token (Generated automatically)
* Re-uses auth token and refreshes it if expired

### Credits:
[NoMore201/googleplay-api](https://github.com/NoMore201/googleplay-api/)