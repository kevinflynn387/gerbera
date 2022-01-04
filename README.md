<img src="https://github.com/gerbera/gerbera/blob/master/artwork/logo-horiz.png?raw=true" />

# Gerbera - UPnP Media Server

 [![Current Release](https://img.shields.io/github/release/gerbera/gerbera.svg?style=for-the-badge)](https://github.com/gerbera/gerbera/releases/latest) [![Build Status](https://img.shields.io/github/workflow/status/gerbera/gerbera/CI%20validation?style=for-the-badge)](https://github.com/gerbera/gerbera/actions?query=workflow%3A%22CI+validation%22+branch%3Amaster) [![Docker Version](https://img.shields.io/docker/v/gerbera/gerbera?color=teal&label=docker&logoColor=white&sort=semver&style=for-the-badge)](https://hub.docker.com/r/gerbera/gerbera/tags?name=1.) [![Documentation Status](https://img.shields.io/readthedocs/gerbera?style=for-the-badge)](http://docs.gerbera.io/en/stable/?badge=stable) [![IRC](https://img.shields.io/badge/IRC-on%20libera.chat-orange.svg?style=for-the-badge)](https://web.libera.chat/?channels=#gerbera)

Gerbera is a UPnP media server which allows you to stream your digital media through your home network and consume it on a variety of UPnP compatible devices.

**Pull requests are very welcome and reporting issues is encouraged.**

## Documentation
View our documentation online at [https://docs.gerbera.io](https://docs.gerbera.io).

## Features
* Browse and playback your media via your network on all kinds of devices.
* Web UI with a tree view of the database and the file system, allowing to add/remove/edit/browse your media
* Metadata extraction from MP3, OGG, AAC, M4A, FLAC, JPG (and many more!) files.
* Media thumbnail support
* Highly flexible media format transcoding via plugins / scripts
* Automatic directory rescans (timed, inotify)
* User defined server layout based on extracted metadata
* Supports last.fm scrobbing
* On the fly video thumbnail generation
* Support for external URLs (create links to internet content and serve them via UPnP to your renderer)
* Runs on Linux, BSD, Mac OS X, and more!
* Runs on x86, ARM, MIPS, and more!

## Installing
Head over to the docs page on [Installing Gerbera](https://docs.gerbera.io/en/stable/install.html) for instructions on
how to install Gerbera.

## Building
Visit our docs for instructions to [Compile Gerbera](https://docs.gerbera.io/en/stable/compile.html) or [Compile latest Gerbera](https://docs.gerbera.io/en/latest/compile.html).

### Quick start build instructions:
```
git clone https://github.com/gerbera/gerbera.git
mkdir build
cd build
cmake ../gerbera -DWITH_DEBUG=YES
make -j4
sudo make install
```

## Dependencies

| Library       | Min Version   | Recommended   | Latest tested | Required?     | Note                       | Default  |
|---------------|---------------|---------------|---------------|---------------|----------------------------|----------|
| libupnp       | 1.14.0        | 1.14.12       | 1.14.12       | XOR libnpupnp | [pupnp]                    |          |
| libnpupnp     | 4.1.2         | 4.1.5         | 4.1.5         | XOR libupnp   | [npupnp]                   | Disabled |
| libuuid       |               |               |               | Depends on OS | Not required on \*BSD      |          |
| [pugixml]     |               | 1.10          | 1.11.4        | Required      | XML file and data support  |          |
| libiconv      |               |               |               | Required      | Charset conversion         |          |
| sqlite3       | 3.7.0         | 3.35.5        | 3.36.0        | Required      | Database storage           |          |
| zlib          |               |               |               | Required      | Data compression           |          |
| [fmtlib]      | 7.1.3         | 7.1.3         | 8.0.1         | Required      | Fast string formatting     |          |
| [spdlog]      | 1.8.1         | 1.8.5         | 1.9.2         | Required      | Runtime logging            |          |
| [duktape]     | 2.1.0         | 2.5.0         | 2.6.0         | Optional      | Scripting Support          | Enabled  |
| mysql         |               |               |               | Optional      | Alternate database storage | Disabled |
| curl          |               |               |               | Optional      | Enables web services       | Enabled  |
| [taglib]      | 1.12          | 1.12          | 1.12          | Optional      | Audio tag support          | Enabled  |
| libmagic      |               |               |               | Optional      | File type detection        | Enabled  |
| [libmatroska] |               | 1.6.3         | 1.6.3         | Optional      | MKV metadata               | Enabled  |
| [libebml]     |               | 1.4.2         | 1.4.2         | Optional      | requird by [libmatroska]   | Enabled  |
| ffmpeg/libav  |               |               |               | Optional      | File metadata              | Disabled |
| libexif       |               |               |               | Optional      | JPEG Exif metadata         | Enabled  |
| [libexiv2]    |               | v0.26         | v0.27.5       | Optional      | Exif, IPTC, XMP metadata   | Disabled |
| [lastfmlib]   | 0.4.0         | 0.4.0         | 0.4.0         | Optional      | Enables scrobbling         | Disabled |
| [ffmpegthumbnailer] |         | 2.2.0         | 2.2.2         | Optional      | Generate video thumbnails  | Disabled |
| inotify       |               |               |               | Optional      | Efficient file monitoring  | Enabled  |


## Licence

    GPLv2

    Copyright (C) 2005
       Gena Batyan <bgeradz at mediatomb dot cc>
       Sergey Bostandzhyan <jin at mediatomb dot cc>

    Copyright (C) 2006-2008
       Gena Batyan <bgeradz at mediatomb dot cc>
       Sergey Bostandzhyan <jin at mediatomb dot cc>
       Leonhard Wimmer <leo at mediatomb dot cc>

    Copyright (C) 2016-2022
        Gerbera Contributors

[Docker Hub]: https://hub.docker.com/r/gerbera/gerbera
[duktape]: http://duktape.org
[ffmpegthumbnailer]: https://github.com/dirkvdb/ffmpegthumbnailer
[fmtlib]: https://github.com/fmtlib/fmt
[lastfmlib]: https://github.com/dirkvdb/lastfmlib
[libebml]: https://github.com/Matroska-Org/libebml
[libexiv2]: https://github.com/Exiv2llibexiv2
[libmatroska]: https://github.com/Matroska-Org/libmatroska
[npupnp]: https://www.lesbonscomptes.com/upmpdcli/index.html
[pugixml]: https://github.com/zeux/pugixml
[pupnp]: https://github.com/pupnp/pupnp
[spdlog]: https://github.com/gabime/spdlog
[taglib]: http://taglib.org/
