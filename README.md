# wpkg-tools

**wpkg-tools** is command line tool to interact with [WPKG](https://wpkg.org/Main_Page) clients from debian, it is written in perl.

## Getting Started

In order to get this running you will need to download wpkg-tools and wpkg-variables.pl and place them in /usr/local/sbin/ with the permissions 700.

You will need to edit wpkg-variables.pl to be correct for your own site.

### Prerequisites

wpkg-tools presumes several things:
 * You are using a debian based operating system
 * You have your WPKG reports stored somewhere accessible
 * You have [wpkgreports.awk](https://github.com/stringydave/wpkgreports) added
 * You have [samba-common](https://packages.ubuntu.com/search?keywords=samba-common) installed
 * You have [perl](https://wiki.debian.org/Perl) installed

There are also several perl components used:
 * [libswitch-perl](https://packages.debian.org/sid/libswitch-perl)
 * [libnet-ping-external-perl](https://packages.debian.org/wheezy/libnet-ping-external-perl)
 * [libterm-readkey-perl](https://packages.debian.org/sid/libterm-readkey-perl)

 ### Installing

 **Downloading scripts:**

It's best to run these commands with sudo or as root

 ```
wget https://raw.githubusercontent.com/Link2Twenty/wpkg-tools/master/wpkg-tools -P /usr/local/sbin/
wget https://raw.githubusercontent.com/Link2Twenty/wpkg-tools/master/wpkg-variables.pl -P /usr/local/sbin/

chmod 700 /usr/local/sbin/wpkg-tools
chmod 700 /usr/local/sbin/wpkg-variables.pl
 ```

 You will have to edit the two variables in /usr/local/sbin/wpkg-variables.pl, using your prefered editor

```
our $user = "username%password";
our $wpkg_reports = "/location/of/wpkgreports";
```

 **Installing prerequisites:**

 ```
apt install samba-common
apt install perl perl-doc

apt install libterm-readkey-perl
apt install libnet-ping-external-perl
apt install libswitch-perl
 ```

 **Updating**

 This should be as simple as running the update script

 ```
server:~# wpkg-tools --update
wpkg-tools is already on the latest version (v0.1.2)
server:~# wpkg-tools --version
v0.1.2
 ```

 ```
server:~# wpkg-tools --update
wpkg-tools will be updated to version v0.1.3
server:~# wpkg-tools --version
v0.1.3
 ```

## Usage

```
Usage: wpkg-tools [OPTION...]
-u, --username       Set a non-default username (password required)
-p, --password       Set a non-default password (string)
-P, --prompt         Set a non-default password (prompt)
-m, --machine        Only run command for one specific computer
-r, --report         Display latest wpkg report
-s, --status         Display current status of WPKG service
-v, --version        Display version of wpkg-tools
--update             Update to latest release of wpkg-tools
-h, -?, --help       Display help screen
```

## Authors

* **Andrew Bone** - [Link2Twenty](https://github.com/Link2Twenty/)
* **Dave Evans** - [stringydave](https://github.com/stringydave/)

## Some links

* Main the WPKG website - https://wpkg.org/
* WPKG documentation page - https://wpkg.org/Documentation
* Article on Wikipedia - https://en.wikipedia.org/wiki/WPKG_(software)

## Acknowledgments
 * [wpkgreports.awk](https://github.com/stringydave/wpkgreports) by [Dave Evans](https://github.com/stringydave/)
