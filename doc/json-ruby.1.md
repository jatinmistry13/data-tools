% JSON-RUBY(1)
% CLARK Grubb
% February 17, 2013


# NAME

json-ruby - read JSON objects from a file or standard input and process them with Ruby 

# SYNOPSIS

json-ruby [-j|-t] [-i] (-f RUBY\_PATH | RUBY\_SCRIPT) [JSON\_INPUT] ...

# DESCRIPTION

Read input containing one JSON object per line and parse it.  Each parsed object is placed in the global accumulator variable $_ where it can be accessed by the Ruby script.

The Ruby script can be provided on the command line or read from the file RUBY\_PATH.

BEGIN and END blocks can be defined in the manner of `awk` to define Ruby code which executes at the start or end of execution.
     
By default the script exits with an error if a line contains invalid JSON.  Use the `-i` flag to keep going.
     
# OPTIONS

-f PATH, \--file=PATH
: execute the Ruby script in the file at PATH.

-i, \--ignore
: ignore lines containing invalid JSON.  A notice is still written to standard error.

-j, \--json
: after the Ruby script is executed, write the contents of $_ to standard output as JSON.

-t, \--tsv
: after the Ruby script is executed, write the contents of $_, which is expected to be an Array, to standard output in tab separated values format.

# SEE ALSO

`awk` (1)

http://json.org/
