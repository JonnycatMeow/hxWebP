# hxWebP

A Haxe/[OpenFL](https://www.openfl.org) library for using WebP files with  [libwebp 1.3.2](https://chromium.googlesource.com/webm/libwebp).

## Why WebP?
As opposed to JPEG, PNG, or GIF files, WebP files are:
- Smaller in size compared to all three
- Can be transparent like PNG files
- Supports both lossy (JPG-like) and lossless (PNG-like) compression
- Can be animated too (like GIFs) while being transparent and lossless!

Unfortunately, as of right now, WebP files are also:
- Unsupported natively on not-HTML5 platforms (leads to converting back to PNG/JPG/GIF files in most circumstances)
- Not easy to encode images into WebP with specific settings

## Supported Features
Very barebones so far! Does the following:
- Decodes WebP files into Image/BitmapData to use in Lime/OpenFL.

## Supported Platforms 
WebP files are supported on the following platforms:
| OS | Status |
| --- | --- |
| Windows | ✔️ (64-bit) |
| macOS | ✔️ |
| Linux | ✔️ |
| HTML5 | ✔️ (natively) |
| Android | 🚧 |
| iOS | 🚧 |

## Installation

Install hxWebP from either source:

* haxelib
   ```bash
   haxelib install hxWebP
   ```

* git
   ```bash
   haxelib git hxWebP https://github.com/Binpuki/hxWebP.git
   ```

## READ THIS if you're a linux user

You need to install libwebp from your distro's package manager (Instructions may vary).

* Debian-based distros (like Ubuntu or... well, Debian)
   ```bash
   sudo apt-get install libwebp-dev webp
   ```

* Arch-based distros
   ```bash
   sudo pacman -S libwebp
   ```

## Usage

Add the library inside your Project.xml file.
```xml
   <haxelib name="hxWebP" if="cpp || web" />
```

You can then use the ```webp.WebP``` class to decode files either from a specified path or binary data.
```haxe
   var bitmapFromFile:BitmapData = WebP.getBitmapData("assets/images/coolimage.webp");
```
```haxe
   var bitmapFromBytes:BitmapData = WebP.getBitmapDataFromBytes(Assets.getBytes("assets/images/coolimage.webp"));
```

## License
**hxWebP** is made available under the **MIT License**. Check [LICENSE](./LICENSE) for more information.

**libwebp** was released under the **BSD License**. Check [webmproject.org](https://www.webmproject.org/license/software/) for more information.

## Credits
- [hxvlc](https://github.com/MAJigsaw77/hxvlc) - Reference on how to link C libraries
- [openfl-webp](https://github.com/soywiz-archive/haxe-openfl-webp) - The original OpenFL WebP library and inspired this project
