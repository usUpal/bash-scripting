# bash-scripting

``` bash
$ touch files_{1..100}.txt
$ echo {1..11} #1 2 3 4 5 6 7 8 9 10 11
$ echo {1..10..2} #1 3 5 7 9
$ 
$ 
```

```bash
$ echo "text" > file.txt #overwrite file.txt
$ echo "text" >> file.txt #append file.txt
$ cat << quote
the quiter you become
the more you can here
quote
```

```bash
choice=4 # no space**
if [ $choice -eq 4 ] ; then
        echo "four"
else
        echo "not four"
fi

```

