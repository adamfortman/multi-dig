# multi-dig

## Description

This bash script is a spin off the basic dig functionality. Default usage finds the domain's authoritative nameservers and performs a lookup of various record types against those nameservers. Records can also be checked against the custom list of public nameservers as well as local resolvers found in `/etc/resolv.conf`.

## Installation -- MacOSX

You must have brew installed -- https://brew.sh/

Modify your PATH to include the gnubin:

```
echo 'PATH=/usr/local/opt/gnu-sed/libexec/gnubin:$PATH' >> ~/.profile
source .profile
```

Now, to actually get everything else set up:
```
brew install gnu-sed
brew install bash
mkdir -vp ~/src
cd ~/src
git clone https://github.com/adamfortman/multi-dig
mkdir ~/bin
ln -s ~/src/multi-dig/mdig ~/bin/mdig
mv -v ~/src/multi-dig/update-mdig-macosx ~/bin/update-mdig
chmod u+x ~/bin/mdig ~/bin/update-mdig
~/bin/update-mdig
```

You should be all set to go!

## Usage

```
Usage: /home/forty/bin/mdig <options> <record(s)> <domain>

Options:
	-h|--help   - prints this message
	--all		- check against authoritative, custom, and local resolvers
	-a|--auth   - check against authoritative resolver list (default)
	-c|--custom - check against custom public resolver list only
	-l|--local  - check against local resolvers found in /etc/resolv.conf
	--nsinfo    - print the authoritative nameservers and their IP addresses

Records default to: SOA A AAAA CAA MX NS TXT
```

