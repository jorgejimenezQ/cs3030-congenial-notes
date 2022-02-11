# AWK

`awk` is a interpreted programming language used to manipulate data and generating reports. `awk` supports variables, math, strings, and logical operations.

## Usage

```bash
Usage: awk [POSIX or GNU style options] -f progfile [--] file ...
Usage: awk [POSIX or GNU style options] [--] 'program' file ...
POSIX options:		GNU long options: (standard)
	-f progfile		                --file=progfile
  -F fs			                    --field-separator=fs
	-v var=val		                --assign=var=val
Short options:		GNU long options: (extensions)
	-b			                      --characters-as-bytes
	-c			                      --traditional
	-C			                      --copyright
	-d[file]		                  --dump-variables[=file]
	-D[file]		                  --debug[=file]
	-e 'program-text'	            --source='program-text'
	-E file		      	            --exec=file
	-g			                      --gen-pot
	-h			                      --help
	-i includefile		            --include=includefile
	-l library		                --load=library
	-L[fatal|invalid|no-ext]	    --lint[=fatal|invalid|no-ext]
	-M		    	                  --bignum
	-N		    	                  --use-lc-numeric
	-n		    	                  --non-decimal-data
	-o[file]		                  --pretty-print[=file]
	-O		    	                  --optimize
	-p[file]		                  --profile[=file]
	-P			                      --posix
	-r			                      --re-interval
	-s			                      --no-optimize
	-S			                      --sandbox
	-t			                      --lint-old
	-V			                      --version

```

## Example Usage

```bash
	gawk '{ sum += $1 }; END { print sum }' file
	gawk -F: '{ print $1 }' /etc/passwd
```

## Example Script

```awk
# Header - seperator. Set field seperator
BEGIN {
    FS=":";
    print "Usernames";
}
# Body of the script
/^h/{

    user=$1
    groupId=$3

    print "\t" user " " groupId
    count++
}

# FOOTER
END {print "Number of users = " count} # Optional
```
