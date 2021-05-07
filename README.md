newsboat-og
===========

Newsboat-og is a fork of Newsboat (https://github.com/newsboat/newsboat) in
it's last version before rustification (version 2.13). The name for "old gen".
This fork tries to keep the C/C++ implementation alive for platforms lacking
a rust compiler.

Newsboat is a fork of Newsbeuter, an RSS/Atom feed reader for the text console.
The only difference is that Newsboat is actively maintained while Newsbeuter
isn't.

If you want the modern version of Newsboat head to https://github.com/newsboat/newsboat.

Dependencies
------------

Newsboat depends on a number of libraries, which need to be installed before
newsboat can be compiled.

- GCC 4.9 or newer, or Clang 3.6 or newer
- [STFL (version 0.21 or newer)](http://www.clifford.at/stfl/)
- [SQLite3 (version 3.5 or newer)](http://www.sqlite.org/download.html)
- [libcurl (version 7.18.0 or newer)](http://curl.haxx.se/download.html)
- GNU gettext (on systems that don't provide gettext in the libc):
  ftp://ftp.gnu.org/gnu/gettext/
- [pkg-config](http://pkg-config.freedesktop.org/wiki/)
- [libxml2, xmllint, and xsltproc](http://xmlsoft.org/downloads.html)
- [json-c (version 0.11 or newer)](https://github.com/json-c/json-c/wiki)
- [asciidoc](http://www.methods.co.nz/asciidoc/INSTALL.html)
- DocBook XML
- DocBook XSL

Installation
------------

First, you'll have to get the dependencies. Make sure to install the header
files for the libraries (on Debian and derivatives, headers are in `-dev`
packages, e.g. `libsqlite3-dev`.) After that, compiling and installing newsboat
is as simple as:

	make
	make install

(And if you ever need to uninstall it, use `make uninstall`.)

Support
-------

* Check out our
  [documentation](https://newsboat.org/releases/2.13/docs/newsboat.html) and
  [FAQ](https://newsboat.org/releases/2.13/docs/faq.html)
* Bugs and whatnot should be reported to the
  [issue tracker](https://github.com/andreasbaumann/newsboat-og/issues)

Development
-----------

Decided to work on an issue, fix a bug or add a feature? Great! Be sure to
check out [our style guide](doc/code-style.markdown) and install pre-commit
hook.

You'll probably want to run the tests; here's how:

	make -j5 PROFILE=1 all test
	(cd test && TMPDIR=/dev/shm ./test --order rand)

Note the use of ramdisk as `TMPDIR`: some tests create temporary files, which
slows them down if `TMPDIR` is on HDD or even SSD.

License
-------

Newsboat is licensed under [the MIT
license](https://opensource.org/licenses/MIT); see the LICENSE file.

Maintainers
-----------

The maintainer of newsboat-og is Andreas Baumann <mail@andreasbaumann.cc>
