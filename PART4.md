# (PART 4) Writing Shell Scripts

#### Assign value to variable & Use Variables

```
TITLE="System Information Report"

echo "
<html>
    <title>$TITLE</title>
</html>
";
```

``CURRENT_TIME="$(date)"``

### Here Documents

```
TITLE="System Information Report for $HOSTNAME"
CURRENT_TIME="$(date + "%x %r %Z)"

cat << _EOF_
<html>
    <head>
        <title>$TITLE</title>
    </head>
    <body>
        <h1>$TITLE</h1>
        <p>$TIMESTAMP</p>
    </body>
</html>

_EOF_

```

``<<- `` => ignore leading tabs

### Here Document example

```
#!/bin/bash

FTP_SERVER=ftp.nl.debian.org
FTP_PATH=/debian/dists/stretch/main/installer-amd64/current/images/cdrom
REMOTE_FILE=debian-cd_info.tar.gz

ftp -n << _EOF_

open $FTP_SERVER
user anonymous me@linuxbox
cd $FTP_PATH
hash

_EOF_


```

### if statements

#### Equality for if statements

```
if [ "$x" -eq 5 ]; then
    echo "x equals 5."
else
    echo "x does not equals 5."
fi
```

### Exit status

![](images/exit_status.png)

### Using test

-   -e  => file exists?
-   -f  => regular file?
-   -d  => directory?

```
    if [-f "$FILE"]; then
        echo "file"
    fi
```

``-z`` => length of string is zero?

``-eq`` => integer1 is equal to integer 2

```
    if [ "$INT" -eq 0]; then
        echo "zero"
    fi
```

### A More Modern Version of test

```
[[ expression ]]

string1 =~ regex

Example:

if [[ "$INT" =~ ^-?[0-9]+$ ]]; then
    echo "INT is zero"
fi
```

### ((  )) - Designed for Integers

```
    # Not use $
    if (( INT == 0 )); then

    fi

```

### Combining expressions
|Operation | test | [[ ]] and (( ))|
|----------|------|----------------|
|AND       | -a   | &&             |
|OR        | -o   | \|\|           |
|NOT       | !    | !              |


### IFS (Internal Field Seperator)

![](images/ifs.png)

#### To trace bash comman, -x parameter can be used.

``#!/bin/bash -x``

`` ${foo:-"If it is not set, value will be this text."} ``

![](images/default_set.png)

!!!!!!!!!!Sayfa 419'dan devam
