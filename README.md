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

## countdown.sh

```bash
#!/bin/bash

m=${1-7200}-1 # add minus 1 || 7200 means 2hours

Floor () {
  DIVIDEND=${1}
  DIVISOR=${2}
  RESULT=$(( ( ${DIVIDEND} - ( ${DIVIDEND} % ${DIVISOR}) )/${DIVISOR} ))
  echo ${RESULT}
}

Timecount(){
        s=${1}
        HOUR=$( Floor ${s} 60/60 )
        s=$((${s}-(60*60*${HOUR})))
        MIN=$( Floor ${s} 60 )
        SEC=$((${s}-60*${MIN}))
     while [ $HOUR -ge 0 ]; do
        while [ $MIN -ge 0 ]; do
                while [ $SEC -ge 0 ]; do
                        printf "%02d:%02d:%02d\033[0K\r" $HOUR $MIN $SEC
                        SEC=$((SEC-1))
                        sleep 1
                done
                SEC=59
                MIN=$((MIN-1))
        done
        MIN=59
        HOUR=$((HOUR-1))
     done
}

Timecount $m
```

