#README for libsocket

##LICENSE

It's recommended to compile libsocket statically into your program (by placing the .c and .h files in your source tree).
You don't have to mind legal issues because libsocket is licensed by a slightly modified 2-clause BSD license which permits
any use, as long as you include the license text in your product (so it's clear that libsocket is licensed by this License)
and the notice that *we* wrote libsocket (as described in the license)
It's friendly to mention libsocket in your product's Readme or advertisements anyway, of course :)

##USE

libsocket is built for little programs whose author(s) are too lazy to build own algorithms and functions for socket (UNIX (coming soon)
and Internet Domain (TCP/UDP)) communication.

As you should know as experienced C programmer, it's quite easy to use this library.
Simply add the line into the source files where the library is used:

	# include "path/to/lib{inet,unix}socket.h"

and call the compiler (eventually in a makefile) with the name of the C file:

	$ gcc lib{inet,unix}socket.c ownfile1.c ownfile2.c
	# or
	$ gcc -c libsocket.c
	$ gcc ownfile1.c ownfile2.c libsocket.o
	# etc. pp.

##FEATURES AND ADVANTAGES

The libsocket library supports following things and protocols:

* IPv4 (client, server)
* IPv6 (client, server; if your machine supports it)
* TCP (client, server)
* UDP (client, server)
* UNIX Domain Sockets (DGRAM&STREAM server/client)
* Intelligent algorithms to get the best connection and no errors
* Easy use (one function call to get a socket up and running, one another to close it)
* Proper error processing (using errno, gai\_strerror() etc.).

One of the main advantages of libsocket is that you don't have to write the complex and error-prone
procedures for connecting a socket, check it on errors etc. yourself.

##PLATFORMS

I'd like to get test reports and experiences from you. I already tested the library under the following conditions:

* Linux 3.1, gcc-4.6, TCP IPv4 sockets
* Linux 3.1, gcc-4.7, TCP IPv4 sockets
* Linux 3.1, gcc-4.7, TCP IPv4 server sockets

It is planned to test and get libsocket working on OpenBSD 5.0. If you want, you may port it anywhere.
