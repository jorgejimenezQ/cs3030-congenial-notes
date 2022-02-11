# Stream Editor

from [digital ocean](https://www.digitalocean.com/community/tutorials/the-basics-of-using-the-sed-stream-editor-to-manipulate-text-in-linux): <br>
"The `sed` command performs editing operations on text coming from standard input or a file."

`sed` manipulates text using a simple and compact programming language.

```bash
> sed [options] commands [file-to-edit]
```

## Usage Examples

```bash
# s = substitute - substitute root with seed
# p = print - print the lines affected
# g = global - substitute all instances of "root" in every line
> sed -n 's/root/seed/gp' mypasswd
```

```bash
# Find and replace "jimenez" in the mypasswd file
> sed -n 's/jimenez/something/gp' mypasswd

# Find and replace "jimenez" and "Jimenez" in the file
# Uses regex
> sed -n 's/[Jj]imenez/something/gp' mypasswd

# Only lines that begin with "jorge"
> sed -n '/^jorge/ s/[Jj]imenez/something/gp' mypasswd
    colors.txt       mypasswd.bak       quanti.txt       subs.sed
      mypasswd         parsecsv.sh        README.md        tools.csv
# To update the file and create a backup
> sed -i.bak '/^bacula/ s/x/color/gp' mypasswd
> ls
    colors.txt       mypasswd.bak       quanti.txt       subs.sed
    mypasswd         parsecsv.sh        README.md       tools.csv
```

## Resources

[Options list](https://etutorials.org/Linux+systems/red+hat+linux+9+professional+secrets/Part+II+Exploring+Red+Hat+Linux/Chapter+8+GNU+Utilities/Stream+Editor+-+sed/#table-titlelabel)
