puppet-minicat(8) -- Make a mini-catalog, to view data-driven template output
=============================================================================

SYNOPSIS
--------
puppet minicat <action> 

DESCRIPTION
-----------
This subcommand eases the debugging of external-data-driven Puppet templates by fetching the External Node
Classifier output from the exec terminus but modifying the list of classes to a user-specified subset.

OPTIONS
-------
Note that any configuration parameter that's valid in the configuration
file is also a valid long argument, although it may or may not be
relevant to the present action. For example, `server` is a valid
configuration parameter, so you can specify `--server <servername>` as
an argument.

See the configuration file documentation at
<http://docs.puppetlabs.com/references/stable/configuration.html> for the
full list of acceptable parameters. A commented list of all
configuration options can also be generated by running puppet with
`--genconfig`.

* --mode MODE:
  The run mode to use for the current action. Valid modes are `user`, `agent`,
  and `master`.
* --render-as FORMAT:
  The format in which to render output. The most common formats are `json`,
  `s` (string), `yaml`, and `console`, but other options such as `dot` are
  sometimes available.
* --verbose:
  Whether to log verbosely.
* --debug:
  Whether to log debug information.

ACTIONS
-------
* `compile` - Compile and display a catalog locally, driven by the node classifier:
  `SYNOPSIS`

  puppet minicat compile <--node NODENAME>
[--classlist puppet::class1,puppet::class2]


  `DESCRIPTION`

  Similar to puppet apply, but with the option to (a) pretend to be a different node and
  (b) modify the list of classes returned by the node classifier


  `OPTIONS`

  <--classlist puppet::class1,puppet::class2> -
  Comma-separated list of classes to include in the compiled catalog (defaults to ENC list if omitted)
  <--node NODENAME> -
  Fetch data from the ENC as if we were this node


COPYRIGHT AND LICENSE
---------------------
Copyright 2012 by Apple Inc
Apache 2.0
