# iota2

> Making Imaginations, Real

<i2.iotasquare@gmail.com>

```
 ██╗ ██████╗ ████████╗ █████╗ ██████╗
 ██║██╔═══██╗╚══██╔══╝██╔══██╗╚════██╗
 ██║██║   ██║   ██║   ███████║ █████╔╝
 ██║██║   ██║   ██║   ██╔══██║██╔═══╝
 ██║╚██████╔╝   ██║   ██║  ██║███████╗
 ╚═╝ ╚═════╝    ╚═╝   ╚═╝  ╚═╝╚══════╝
```

[![BSD licensed](https://img.shields.io/badge/license-GPL3-blue.svg)](https://raw.githubusercontent.com/iota2/dev-setup/master/LICENSE)


# Installing libcaop with DTLS

**CoAP Specifications:** http://coap.technology/

**libcoap:**  https://libcoap.net/

**libcoap GIT Repository:** https://github.com/obgm/libcoap

**libcoap Help Reference:** https://libcoap.net/doc/reference/4.2.1/

**More Details:** https://docs.zephyrproject.org/1.12.0/samples/net/coaps_server/README.html


### libcoap Installation
```
$ git clone --recursive -b dtls https://github.com/obgm/libcoap.git
$ cd libcoap/
$ sudo apt-get install libtool asciidoc --fix-missing
$ ./autogen.sh
$ ./configure --disable-shared
$ make all
```
After completing the installation, DTLS enabled libcaop script will be
available under `libcoap/examples` as `coap-client`:
```
$ ./coap-client -m get coaps://address:port/test -u "identity" -k "password"
```

Also we can create a common folder and put all user specific scripts there.
Then we can export it's path to make scripts in this folder available
throughout the system.

> we can also add the `export PATH=$PATH:/$HOME/bin` to `~/.bashrc` file so
that it is available every time we launch the terminal.

```
$ mkdir ~/bin
$ cp coap-client ~/bin/.
$ export PATH=$PATH:/$HOME/bin
$ source $HOME/.bashrc
```

# License
> `GNU GPU v3` <br>
> This program is free software; you can redistribute it and/or
> modify it under the terms of the GNU General Public License
> as published by the Free Software Foundation; either version 3
> of the License, or (at your option) any later version.
> This program is distributed in the hope that it will be useful,
> but WITHOUT ANY WARRANTY; without even the implied warranty of
> MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
> GNU General Public License for more details.

**Free Software, Hell Yeah!**

