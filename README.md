# libimobiledevice

## About

A library to communicate with services of Apple iOS devices using native
protocols.

## Requirements

Development Packages of:
* OpenSSL or GnuTLS
* libplist
* libusbmuxd

Software:
* usbmuxd (OSS or Apple's version)
* make
* autoheader
* automake
* autoconf
* libtool
* pkg-config
* gcc or clang

Optional:
* cython (Python bindings)
* doxygen (Documentation)

## Installation

To compile run:
```bash
./autogen.sh
make
sudo make install
```

If you require a custom prefix or other option being passed to `./configure`
you can pass them directly to `./autogen.sh` like this:
```bash
./autogen.sh --prefix=/opt/local --enable-debug-code
make
sudo make install
```

By default, OpenSSL will be used. If you prefer GnuTLS, configure with
`--disable-openssl` like this:
```bash
./autogen.sh --disable-openssl
```
## ./autogen.sh --disable-openssl错误
1. Requested 'libusbmuxd >= 1.1.0' but version of libusbmuxd is 1.0.10

###
	brew update
	brew uninstall --ignore-dependencies libimobiledevice
	brew uninstall --ignore-dependencies usbmuxd
	brew install --HEAD usbmuxd
	brew unlink usbmuxd
	brew link usbmuxd
	brew install --HEAD libimobiledevice
###
2.gnutls缺失
###
	brew install gnutls
	brew install libgcrypt
###
3.提示libxxx缺失
###
	brew install libxxx...
###

直到没有任何错误, 运行./autogen.sh --disable-openssl, 然后make

## Who/What/Where?

* Home: https://www.libimobiledevice.org/
* Code: `git clone https://git.libimobiledevice.org/libimobiledevice.git`
* Code (Mirror): `git clone https://github.com/libimobiledevice/libimobiledevice.git`
* Tickets: https://github.com/libimobiledevice/libimobiledevice/issues
* Mailing List: https://lists.libimobiledevice.org/mailman/listinfo/libimobiledevice-devel
* IRC: irc://irc.freenode.net#libimobiledevice
* Twitter: https://twitter.com/libimobiledev

## Credits

Apple, iPhone, iPod, and iPod Touch are trademarks of Apple Inc.
libimobiledevice is an independent software library and has not been
authorized, sponsored, or otherwise approved by Apple Inc.

README Updated on: 2019-06-21
