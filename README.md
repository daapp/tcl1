tcl1 - frontend for one liner tcl scripts, as replacement for AWK.

# Dependencies

- tcllib (cmdline)

# Options

- **-n** - loop over input lines, variable $_ contains current line
- **-p** - loop over input lines and print result of last expression, variable $_ contains current line
- **-I** - do not read file ~/.tcl1

# Examples

Add folowing string to ~/.tcl1:
```tcl
interp alist {} str {} string
```

This allow to cut command "string" to "str".

Check, how tcl1 works:
```tcl
tcl1 'puts {Tcl1 works!}'
```

Iterate over input and print each line if it is a direcory name inside /:
```tcl
ls -1 / | tcl1 -n 'if {[file isdir /$_]} {puts "< $_ >"}' 
```

Iterate over input and print each modified line:
```tcl
ls -1 / | tcl1 -p 'str totitle $_'
```

