![Noto](images/noto.png)
# Noto Emoji
Color and Black-and-White Noto emoji fonts, and tools for working with them.

## Prerequisites
- This project uses Python 3. 
- You need either [zopflipng](https://github.com/google/zopfli) or [optipng](ttp://optipng.sourceforge.net/). (Zopflipng is better (about 5-10%) but much slower.)
- You need [pkg-config](https://www.freedesktop.org/wiki/Software/pkg-config/)


## Building NotoColorEmoji
This project uses a virtual environment to manage dependencies. Use the following steps to get up and running.

Create a virtual environment called `noto-emoji-env`:

	python3 -m venv noto-emoji-env

Activate the virtual environment:

	source noto-emoji-env/bin/activate

Install the Python requirements with:
	
	pip install -r requirements.txt

Then run `make`.  NotoColorEmoji is the default target.  It's suggested to use -j,
especially if you are using zopflipng for compression.  Intermediate products
(compressed image files, for example) will be put into a build subdirectory; the
font will be at the top level.

## Using NotoColorEmoji

NotoColorEmoji uses the CBDT/CBLC color font format, which is supported by Android
and Chrome/Chromium OS.  Windows supports it starting with Windows 10 Anniversary
Update in Chome and Edge.  On macOS, only Chrome supports it, while on Linux it will
support it with some fontconfig tweaking, see [issue #36](https://github.com/googlei18n/noto-emoji/issues/36). Currently we do not build other color font formats.

## Color emoji assets

The assets provided in the repo are all those used to build the NotoColorEmoji
font.  Note however that NotoColorEmoji often uses the same assets to represent
different character sequences-- notably, most gender-neutral characters or
sequences are represented using assets named after one of the gendered
sequences.  This means that some sequences appear to be missing.  Definitions of
the aliasing used appear in the emoji_aliases.txt file.

Also note that the images in the font might differ from the original assets.  In
particular the flag images in the font are PNG images to which transforms have
been applied to standardize the size and generate the wave and border shadow.  We
do not have SVG versions that reflect these transforms.

## B/W emoji font

The black-and-white emoji font is not under active development.  Its repertoire of
emoji is now several years old, and the design does not reflect the current color
emoji design.  Currently we have no plans to update this font.

## License

Emoji fonts (under the fonts subdirectory) are under the
[SIL Open Font License, version 1.1](fonts/LICENSE).<br/>
Tools and most image resources are under the [Apache license, version 2.0](./LICENSE).
Flag images under third_party/region-flags are in the public domain or
otherwise exempt from copyright ([more info](third_party/region-flags/LICENSE)).

## Contributing

Please read [CONTRIBUTING](CONTRIBUTING.md) if you are thinking of contributing to this project.

## News

* 2017-09-13: Emoji redesign released.
* 2015-12-09: Unicode 7 and 8 emoji image data (.png format) added.
* 2015-09-29: All Noto fonts now licensed under the SIL Open Font License.
