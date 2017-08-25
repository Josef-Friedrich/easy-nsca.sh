[![Build Status](https://travis-ci.org/JosefFriedrich-shell/easy-nsca.sh.svg?branch=master)](https://travis-ci.org/JosefFriedrich-shell/easy-nsca.sh)

# easy-nsca.sh


## Summary / Short description

> A convenient script wrapper around send_nsca.

## Usage

```
Usage: skeleton.sh [<options>] <service> <check-command>

A convenient script wrapper around send_nsca.

Environment variables: (to place in your *rc files of your shell)

	- NSCA_SERVER
	- NSCA_CONFIG
	- PATH_CHECK

export NSCA_SERVER="123.123.123.123"
export NSCA_CONFIG="/etc/send_nsca.cfg"
export PATH_CHECK="/usr/lib/nagios/plugins"

Options:
	-c NSCA_CONFIG:    NSCA config file (default: /etc/send_nsca.cfg)
	-h:                Show this help.
	-H NSCA_SERVER:    IP address of the Nagios server.
	-n HOST_SERVICE:   Host of the service.
	-p PATH_CHECK:     Folder containing the check commands.
	                   (default: /usr/lib/nagios/plugins)
	-o OUTPUT:         Output of the check commands.
	-r RETURN:         Plugin return codes: 0 Ok, 1 Warning,
	                   2 Critical, 3 Unkown.

Examples:

skeleton.sh "APT" "check_apt -t 100"
skeleton.sh "Disk space" "check_disk -w 10% -c 5% /dev/sda1"
```
## Testing

```
make test
```

