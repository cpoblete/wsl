# WSL
Wsman Shell commandLine
(pronounced "whistle") is a set of shell scripts that serve as a commandline client to WSMAN.

# DESCRIPTION

WSL contains various scripts that serve as a client interface to WSMAN or
Web Services for Management protocol based on DMTF standard specification.
WSMAN provides standards based messaging for systems management CIM-style
objects.

WSL is "lightweight" because it is composed of scripts (that is no binary)
and is dependent on tools that are already present on standard installation
or readily available to UNIX-like operating systems.

# REQUIREMENTS

The tools in this package requires the following to run:

 * bash and other GNU core utilities such as sed, awk and grep
 * curl - utility for getting files from remote (HTTP/HTTS) servers
 * xmllint - LIBXML2 utility
 * (optional) xsltproc - LIBXML2 utility for output formatting
 * (optional) gpg - encryption utility for password
 * (optional) wget - alternate to curl

It may run on Windows operating system by installing CYGWIN or similar
port of GNU shell environment and tools.

# EXECUTION

Each script shall have its own usage help text.

You can customize run-time experience by defining variables in the shell 
environment or in a ".wslrc" file located in the program or user home or
current directories loaded in this order.
 
Connection variables:

	USEWGET - Use wget for transmission. Default is curl.
	WGETTIMEOUTSECS - Wget timeout in seconds waiting for response. { 1...600} Default is 60.
	WGETTRYNUM - Wget number of retry when there is no response. { 1...6 } Default is 1.
	WSNOSSL - Use HTTP connection. Default is use HTTPS.
 
Wsman options:

	WSENUMMAXELEM - Max number of instances in a response. { 1...1048576 } Default is 512.
	WSENUMOPTIMIZE - Optimized enumeration. Default is non-optimized.
	WSDEFAULTSCHEMA - Schema prefix used for non-DMTF class. Default is "schemas.dell.com"
	WSOPERATIONTIMEOUT - WSMAN operation timeout in seconds. Default is none specified.
	WSMAXENVELOPESIZE - Max SOAP envelope size client will accept. Default is none specified.
 
User input:

	IPINTERACTIVE - Always ask for IP address. Default is use history.
	KEEPHISTORY - Remember IP address and user credential. Default is keep history.
 
Output behavior:

	DATETIMESTAMP - Display date-time stamp. Default is disabled.
	FORMATDISPLAY - Formatted display of response XML. Default is disabled.
	OUTLEVEL - Output level: 0=NoOutput, 1=AddResponse, 2=AddRequest, 3=AddMore. Default is 1.
	OUTPREFIX - Output directory. Default is current directory.
	LOGFILE - Log filename. Default is $OUTPREFIX/log.txt
	RETURNFILE - Result XML filename. Default=$OUTPREFIX/response.xml

# USE AGREEMENT

See accompanying LICENSE file. 
