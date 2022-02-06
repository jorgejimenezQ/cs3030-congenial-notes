# Functions

All functions must go at the top of the script

```bash
help_func()
{
  echo "Help function"
}

help_func
```

## Alternative Functions

```bash
function function_name()
{
  ...
}
```

To call the function just use the name of the function

# Function Parameters

Function parameters work the same way as cmd line arguments

```bash

add()
{
  a=$1
  b=$2
  sum=$(( a + b ))
  echo "$a+$b = $c"

}

add 2 3

```

# Returning From functions

A function in bash can only return an interger

```bash
test()
{
  if [[ -f "nonexistingfile" ]]
  then
    return 0
  fi

  return 1
}

if [[ $? -eq 0 ]]
then
  exit 0
fi

exit 1

```

# Scope

Unlike other languages(Java, JavaScript etc.), variables are not locally scoped automatically. You have to use the key word **`local`**.
