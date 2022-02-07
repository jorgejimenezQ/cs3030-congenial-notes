# Getopts

A built-in Unix shell command for parsing command-line arguments. It is designed to process command line arguments that follow the POSIX Utility Syntax Guidelines, based on the C interface of getopt.

**`Example:`**

```bash
unset FIELD
unset FILE

# Create a help function
usage()
{
    echo "Usage $0 [ -n field ] [-f file_name ]" 1>&2
    exit 0
}

sort_file()
{
	local FIELD=$1
	local FILE=$2

	# parse, sort, and display file
	sort $FILE | uniq | cut -d ":" -f $FIELD
}

# Main file
if [[ $1 == "--help" ]]
then
    usage
fi

# Support getopts frunctionality, support -n choice
# If your choices require an argument use colon separated arguments
while getopts ":n:f:" option
do
    case ${option} in
        n)
            FIELD=${OPTARG}
            echo "-n $FIELD input"
        	;;
		f)
			FILE=${OPTARG}
			echo
			;;
		# Print argument error
		:)
			echo "Invalid option $OPTARG requires an argument"
			usage
			;;
        \?)
            echo "Invalid Option ${OPTARG}"
            usage
        	;;
    esac
done
# shift is a bash built-in which kind of removes arguments from the beginning of the argument list.
shift $((OPTIND -1))

# check required parameters
if [[ -z $FIELD ]] || [[ -z $FILE ]]
then
    echo "Missing required parameter"
	usage
fi

# Display sorted names from records
sort_file $FIELD $FILE

exit 0
```
