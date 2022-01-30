# Exit Codes

When you run a program in bash the program stores an exit code in `$?`

Example:
```bash
~$ printf "%v" "hello"
printf: %v: invalid directive
~$ echo $?
1
```

# Tests in Bash
To run a test in bash use `[[ ... ]]` or `test <FILE or Expression>`
 
 ### Options
 - `-e` test if file exist
 - `-f` test for a regular file
 - `-d` test for a directory
 - `-h or -L` test for symbolic link
  
![terminal example](./test.png)

## Conditional Execution 
The basic `if` command evaluates a list of one or more command

```bash
if <condition>
then 
    <list>
fi
```

## Looping
`**While**` loop 
```bash
n=0
while [[ n -le 10 ]]
do
    echo $n
    n=$(( $n + 1 ))
done
```

# For loop

Works like a `for each`

```bash
# Do something ten times
for num in {1..10} 
do 
    <ITEM>
done
```
# Command Line Arguments
`$@` holds all the arguments passed in

```bash

# Display command line arguments
pre=:
post=:

# $@ array of all command line argumnet s not including $0
for arg in $@
do
    printf "$pre%s$post\n" "$arg"
done

# Equevalent
printf "$pre%s$post\n" "$@"
```