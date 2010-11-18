APIs
====

kXML2
-----

It's a *BSD*-licensed *XML* pull parser, especially adequate (or so they say) for *Java Mobile*. It's small and unobtrusive. You can read more at [kXML2].

AlbiteZIP
---------

It's a *Java Mobile* port of [Classpath]'s `java.util.zip` package using the [AlbiteRandomReadingFile] API, which implements a `RandomAccessFile` with writing capabilities stripped away. Reading *EPUB* files relies on [AlbiteZIP] to work with their archives. AlbiteZIP's sources and some sample code are available at [AlbiteZIP].

AlbiteCharacterDecoder
----------------------

Provides the ability read characters not natively supported by *Java*'s `InputStreamReader`. The API is based on some code from [libiconv]. Sources, examples, tests and binaries are available at [AlbiteCharacterDecoder].

AlbiteUnits
-----------

A simple Java API for converting various physical units. Sources and binaries at [AlbiteUnits].

ZLTextTeXHyphenator
-------------------

I've made a port of *zlibrary*'s hyphenator used in [FBReaderJ]. Licensed under GPL 2.

Fonts
=====

Droid Serif
-----------

That's the font used on *Android* devices. It's really nice and it's built with the idea to render well on small screens and at small sizes. It supports some good amount of glyphs (around 500) and character ranges. It's licensed under the Apache 2.0 license.

Building fonts
--------------

In order to use the font in [AlbiteREADER] you need to build it in the right format.

Firstly, install [BFG]. Now, you need to create a bitmap font using the app. We need a bitmap font with xml descriptor, so BFG will produce a png with a xml file. Take care to hold all the glyphs on a single page and make the page's area as small as possible.

Then, you need to manually edit the newly created xml file in a suitable form. This time you need to use [AlbiteFontBuilder], which will produce the final files. See its page for more info.

Note that in order to implement italic text you need to have two fonts, i.e. two versions of the same font.

If the process is still unclear, you'd better explore the files of the font resources used in [AlbiteREADER].

Hyphenation patterns
====================

The used hyphenation patterns are the ones from [TeX]'s site or some modified versions from [FBReaderJ].

Building the patterns
---------------------

For every language you need to have the patterns in a separate txt file. Each patterns should be on a separate line. Then run [AlbiteTeXBuilder] to build the file that will be used in [AlbiteREADER].

Dictionaries
============

There are some dictionaries ready for download!

- Merriam-Webster 1913, Abridged version (5.5 MB) based on [OPTED]. Abridged using the [3esl] wordlist.
- Merriam-Webster 1913, Full version (13.6 MB) based on [OPTED]. Note that the index alone is 1.5MB large, so you need a device with loads of free memory and fast implementation of the File API.
- Some glossaries from Wiktionary. Include: Architecture Terminology, British Firefighters Jargon, Chess Terms, Irish Slang and Jargon, Library and Information Science, Military Slang, Nautical terms, Scottish Slang, South-African Slang, Truckspeak, US Navy Slang.

Note that the in order to be used in [AlbiteREADER] the dictionaries must be unzipped first.

Building your own dictionaries
-------------------------------

Dictionaries are prepared as *XML* files that are then converted into binary files using [AlbiteDictionaryBuilder]. Dictionary entries can also be filtered against a wordlist so that one can automatically create abridged editions. See the page of the tool for some more exhausting information.

Graphics
========

Most graphics are made by me, except for the book icon that is made by [SimioGraphics] and the tiny icons of the folders, files, the check icon and the broken image icon that I downloaded from the internet.

Building the graphics
---------------------

You need to use [AlbiteImageBuilder] to build the images into the binary format.


[AlbiteREADER]: 			http://github.com/dumbledore/AlbiteREADER
[kXML2]: 					http://kxml.sourceforge.net/kxml2/ 						"their homepage"
[Classpath]: 				http://www.gnu.org/software/classpath/ 					"GNU Classpath"
[AlbiteRandomReadingFile]: 	http://github.com/dumbledore/AlbiteRandomReadingFile
[AlbiteZIP]: 				http://github.com/dumbledore/AlbiteZIP
[libiconv]: 				http://www.gnu.org/software/libiconv/
[AlbiteCharacterDecoder]: 	http://github.com/dumbledore/AlbiteCharacterDecoder
[AlbiteUnits]: 				http://github.com/dumbledore/AlbiteUnits
[FBReaderJ]: 				http://www.fbreader.org/FBReaderJ/
[BFG]: 						http://www.angelcode.com/products/bmfont/				"AngelCode Bitmap Font Generator"
[AlbiteFontBuilder]: 		http://github.com/dumbledore/AlbiteFontBuilder
[TeX]: 						http://www.tug.org/tex-hyphen/
[AlbiteTeXBuilder]: 		http://github.com/dumbledore/AlbiteTeXBuilder
[OPTED]: 					http://www.mso.anu.edu.au/~ralph/OPTED/index.html
[3esl]: 					http://wordlist.sourceforge.net/12dicts-readme.html
[AlbiteDictionaryBuilder]: 	http://github.com/dumbledore/AlbiteDictionaryBuilder
[SimioGraphics]: 			http://simiographics.deviantart.com/
[AlbiteImageBuilder]:		http://github.com/dumbledore/AlbiteImageConverter
