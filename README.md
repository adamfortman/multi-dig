# multi-dig

## Description

This bash script is a spin off the basic dig functionality. Default usage finds the domain's authoritative nameservers and performs a lookup of various record types against those nameservers. Records can also be checked against the custom list of public nameservers.


## Usage

Usage: ./mdig <option> <domain>
	Options:

	-h|--how2 - prints this message
	-b - check against authoritative and custom public nameserver list

	-c - check against custom public nameserver list only


	Notes:
		* defaults to checking authoritative only
