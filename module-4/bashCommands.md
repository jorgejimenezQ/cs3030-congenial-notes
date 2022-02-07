# Grep

Grep is a command-line utility for searching plain-text data sets for lines that match a regular expression.

`Options`:

- `-c` gives you the number of matches

# Cut

The cut command in UNIX is a command for cutting out the sections from each line of files and writing the result to standard output.

## The following command separates the colon separated file in to columns and gives you the specified column

```bash
> cut -d ":" -f 1 <path to file>
```

Example output:

```bash
01/13/2021
06/28/2020
02/05/2021
11/15/2020
05/04/2021
06/24/2020
09/14/2021
08/10/2021
```

# Head

It is the complementary of Tail command. The head command, as the name implies, print the `top N` number of data of the given input.

# Tail

Gives you the bottom n number of lines

## Example

```bash
> cat data.foo
Name:City:Date
Sonya:Verrayes:10/18/2021
Chanda:Mülheim:04/05/2021
Addison:Alwar:05/24/2020
Amena:Neustrelitz:08/24/2020
Cherokee:Le Grand-Quevilly:02/16/2020
Dacey:Aurillac:11/24/2021
Isabella:Habergy:06/20/2020
Hannah:Ichalkaranji:06/24/2020
Perry:Sambreville:09/18/2020
Andrew:Griesheim:01/17/2020

# Get the number of lines in the file
> wc -l data.foo
11
# Get the last 10 lines from the file
# and split them and get the 3rd column
> tail -n 10 | cut -d ":" -f 1 data.foo
10/18/2021
04/05/2021
05/24/2020
08/24/2020
02/16/2020
11/24/2021
06/20/2020
06/24/2020
09/18/2020
01/17/2020

# We can further split the output
> tail -n 10 | cut -d ":" -f 1  | cut -d "/" -f 3
# We get only the year from the output above
2021
2021
2021
2020
2020
2020
2021
2020
2020
2020
2020

```

# Sort

SORT command is used to sort a file, arranging the records in a particular order. By default, the sort command sorts file assuming the contents are ASCII. Using options in the sort command can also be used to sort numerically

# Unique

The uniq command in Linux is a command-line utility that reports or filters out the repeated lines in a file.

## Example

```bash
# Get the last 20 records and split them by colon
# and get the first column then sort them in reverse
❯ tail -n 20 data.foo | cut -d ":" -f 1 | sort -r
Troy
Sonya
Rhiannon
Perry
Mufutau
Michael
Marsden
Isabella
Haviva
Hannah
Declan
Dacey
Cherokee
Chanda
Barrett
Andrew
Amena
Aline
Aladdin
Addison

# Lets see how many lines are in the file
> wc -l data.foo
121
# We only want the unique records of the first column
❯ cut -d ":" -f 1 sample_data | sort -r | uniq | wc -l
98 # there are 22 repeated records

```
