ejabberd Community Edition
==========================

[![CI](https://github.com/processone/ejabberd/actions/workflows/ci.yml/badge.svg)](https://github.com/processone/ejabberd/actions/workflows/ci.yml)
[![Coverage Status](https://coveralls.io/repos/github/processone/ejabberd/badge.svg?branch=master "Coverage in coveralls.io")](https://coveralls.io/github/processone/ejabberd?branch=master)
[![Translation status](https://hosted.weblate.org/widgets/ejabberd/-/ejabberd-po/svg-badge.svg "Translation status in Weblate")](https://hosted.weblate.org/projects/ejabberd/ejabberd-po/)
[![Hex version](https://img.shields.io/hexpm/v/ejabberd.svg "Hex version")](https://hex.pm/packages/ejabberd)

ejabberd is a distributed, fault-tolerant technology that allows the creation
of large-scale instant messaging applications. The server can reliably support
thousands of simultaneous users on a single node and has been designed to
provide exceptional standards of fault tolerance. As an open source
technology, based on industry-standards, ejabberd can be used to build bespoke
solutions very cost effectively.


Key Features
------------

- **Cross-platform**  
  ejabberd runs under Microsoft Windows and Unix-derived systems such as
  Linux, FreeBSD and NetBSD.

- **Distributed**  
  You can run ejabberd on a cluster of machines and all of them will serve the
  same XMPP domain(s). When you need more capacity you can simply add a new
  cheap node to your cluster. Accordingly, you do not need to buy an expensive
  high-end machine to support tens of thousands concurrent users.

- **Fault-tolerant**  
  You can deploy an ejabberd cluster so that all the information required for
  a properly working service will be replicated permanently on all nodes. This
  means that if one of the nodes crashes, the others will continue working
  without disruption. In addition, nodes also can be added or replaced ‘on
  the fly’.

- **Administrator-friendly**  
  ejabberd is built on top of the Open Source Erlang. As a result you do not
  need to install an external database, an external web server, amongst others
  because everything is already included, and ready to run out of the box.
  Other administrator benefits include:
  - Comprehensive documentation.
  - Straightforward installers for Linux.
  - Docker packaging to help with deploy / development on Linux, Windows or MacOS.
  - Deb and RPM packaging to support most Linux distributions.
  - Web administration.
  - Shared roster groups.
  - Command line administration tool.
  - Can integrate with existing authentication mechanisms.
  - Capability to send announce messages.

- **Internationalized**  
  ejabberd leads in internationalization. Hence it is very well suited in a
  globalized world. Related features are:
  - Translated to 25 languages.
  - Support for IDNA.

- **Open Standards**  
  ejabberd is the first Open Source XMPP server claiming to fully comply to
  the XMPP standard.
  - Fully XMPP-compliant.
  - XML-based protocol.
  - Many protocols supported.


Additional Features
-------------------

Moreover, ejabberd comes with a wide range of other state-of-the-art features:

- **Modularity**
  - Load only the modules you want.
  - Extend ejabberd with your own custom modules.

- **Security**
  - SASL and STARTTLS for c2s and s2s connections.
  - STARTTLS and Dialback s2s connections.
  - Web Admin accessible via HTTPS secure access.

- **Databases**
  - Internal database for fast deployment (Mnesia).
  - Native MySQL support.
  - Native PostgreSQL support.
  - ODBC data storage support.
  - Microsoft SQL Server support.

- **Authentication**
  - Internal authentication.
  - PAM, LDAP and ODBC.
  - External authentication script.

- **Others**
  - Support for virtual hosting.
  - Compressing XML streams with Stream Compression (XEP-0138).
  - Statistics via Statistics Gathering (XEP-0039).
  - IPv6 support both for c2s and s2s connections.
  - Multi-User Chat module with support for clustering and HTML logging.
  - Users Directory based on users vCards.
  - Publish-Subscribe component with support for Personal Eventing.
  - Support for web clients: HTTP Polling and HTTP Binding (BOSH).
  - Component support: interface with networks such as AIM, ICQ and MSN.


Quickstart guide
----------------

### 0. Requirements

To compile ejabberd you need:

 - GNU Make.
 - GCC.
 - Libexpat ≥ 1.95.
 - Libyaml ≥ 0.1.4.
 - Erlang/OTP ≥ 19.3.
 - OpenSSL ≥ 1.0.0.
 - Zlib ≥ 1.2.3, for Stream Compression support (XEP-0138). Optional.
 - PAM library. Optional. For Pluggable Authentication Modules (PAM).
 - ImageMagick's Convert program and Ghostscript fonts. Optional. For CAPTCHA
   challenges.
 - Elixir ≥ 1.10.3. Optional. Alternative to build ejabberd

If your system splits packages in libraries and development headers, you must
install the development packages also.

### 1. Compile and install on *nix systems

To compile ejabberd, execute the following commands.  The first one is only
necessary if your source tree didn't come with a `configure` script (In this
case you need autoconf installed).

    ./autogen.sh
    ./configure
    make

To install ejabberd, run this command with system administrator rights (root
user):

    sudo make install

These commands will:

- Install the configuration files in `/etc/ejabberd/`
- Install ejabberd binary, header and runtime files in `/lib/ejabberd/`
- Install the administration script: `/sbin/ejabberdctl`
- Install ejabberd documentation in `/share/doc/ejabberd/`
- Create a spool directory: `/var/lib/ejabberd/`
- Create a directory for log files: `/var/log/ejabberd/`


### 2. Start ejabberd

You can use the `ejabberdctl` command line administration script to
start and stop ejabberd. For example:

    ejabberdctl start


For detailed information please refer to the
[ejabberd Documentation](https://docs.ejabberd.im)


### 3. Use ejabberd locally

Alternatively, you can setup ejabberd without installing in your system:

    ./configure --with-rebar=rebar3
    make dev

Or, if you have Elixir available and plan to develop Elixir code:

    ./configure --with-rebar=mix
    make dev

Check the full list of targets:

    make help


Translation
-----------

Using any gettext editor, you can improve the translation files found in
`priv/msgs/*.po`, and then submit your changes.

Alternatively, a simple way to improve translations is using our Weblate project:
https://hosted.weblate.org/projects/ejabberd/ejabberd-po/


Links
-----

- Documentation: https://docs.ejabberd.im
- Community site: https://www.ejabberd.im
- ejabberd commercial offering and support: https://www.process-one.net/en/ejabberd
