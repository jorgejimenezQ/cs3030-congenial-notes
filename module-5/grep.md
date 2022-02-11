# GREP Command & REGEX

The grep searches a file for the provided pattern

## Common Options

```
Options Description

-c : This prints only a count of the lines that match a pattern
-h : Display the matched lines, but do not display the filenames.
-i : Ignores, case for matching
-l : Displays list of a filenames only.
-n : Display the matched lines and their line numbers.
-v : This prints out all the lines that do not matches the pattern
-e exp : Specifies expression with this option. Can use multiple times.
-f file : Takes patterns from file, one per line.
-E : Treats pattern as an extended regular expression (ERE)
-w : Match whole word
-o : Print only the matched parts of a matching line,
 with each such part on a separate output line.

-A n : Prints searched line and nlines after the result.
-B n : Prints searched line and n line before the result.
-C n : Prints searched line and n lines after before the result.
```

## Example

```bash
❯ grep -E "rotate [17]$" /etc/logrotate.d/*
/etc/logrotate.d/bootlog:    rotate 7
/etc/logrotate.d/btmp:    rotate 1
/etc/logrotate.d/cups-daemon:	rotate 7
/etc/logrotate.d/lightdm:    rotate 7
/etc/logrotate.d/rsyslog:	rotate 7
/etc/logrotate.d/speech-dispatcher:  rotate 7
/etc/logrotate.d/wtmp:    rotate 1
```
