# Jeremy Gautama

https://overthewire.org/wargames/bandit/

## LEVEL 0

> THE PASSWORD is `bandit0`

1. Input the following commands on your terminal:
    ```bash
    ssh -p 2220 bandit0@bandit.labs.overthewire.org
    ```

2. Enter the password: `bandit0`

Summary: When you want to specify a port for ssh in the terminal, you can use `-p [port number]`.

## LEVEL 0 -> LEVEL 1

> THE PASSWORD is `ZjLjTmM6FvvyRnrb2rfNWOZOTa6ip5If`

1. Log into bandit0 with the steps from LEVEL 0.

2. Type in `ls`, which will show a readme file. 
    ```bash
    bandit0@bandit:~$ ls
    readme
    ```

3. Then type in `cat readme`, which will show the following
    ```bash
    bandit0@bandit:~$ cat readme
    ```
    ```
    Congratulations on your first steps into the bandit game!!
    Please make sure you have read the rules at https://overthewire.org/rules/
    If you are following a course, workshop, walthrough or other educational activity,
    please inform the instructor about the rules as well and encourage them to
    contribute to the OverTheWire community so we can keep these games free!

    The password you are looking for is: ZjLjTmM6FvvyRnrb2rfNWOZOTa6ip5If
    ```

Summary: `cat` enables you to see the file you choose.

## LEVEL 1 -> LEVEL 2

> THE PASSWORD is `263JGJPfgU6LtdEvgfWU1XP5yac29mFx`

1. Log into bandit1 in the terminal by:
    ```bash
    ssh -p 2220 bandit1@bandit.labs.overthewire.org
    ```

2. Enter the password: `ZjLjTmM6FvvyRnrb2rfNWOZOTa6ip5If`

3. Enter `ls` to see what files are there:
    ```bash
    bandit1@bandit:~$ ls
    -
    ```

4. To view a dash file, use `cat ./-`
    ```bash
    bandit1@bandit:~$ cat ./-
    263JGJPfgU6LtdEvgfWU1XP5yac29mFx
    ```
    Which is the password we're looking for.

Summary: Viewing a dash file cannot be instantly done by doing `cat -`, but also having a `./` infront of the dash, making it `cat ./-`.

## LEVEL 2 -> LEVEL 3

> THE PASSWORD is `MNk8KNH3Usiio41PRUEoDFPqfxLPlSmx`

1. Log into bandit2 in the terminal by:
    ```bash
    ssh -p 2220 bandit2@bandit.labs.overthewire.org
    ```

2. Enter the password: `263JGJPfgU6LtdEvgfWU1XP5yac29mFx`

3. Enter `ls` to see what files are there:
    ```bash
    bandit2@bandit:~$ ls
    spaces in this filename
    ```

4. To view files with spaces, use a backslash before the space `\ ` like so:
    ```bash
    bandit2@bandit:~$ cat spaces\ in\ this\ filename
    MNk8KNH3Usiio41PRUEoDFPqfxLPlSmx
    ```
    Which is the password we're looking for.

Summary: To view files with spaces, use a backslash after the first word, then a space, and the next word, and so on `\ `.

## LEVEL 3 -> LEVEL 4

> THE PASSWORD is `2WmrDFRmJIq3IPxneAaMGhap0pFhF3NJ`

1. Log into bandit3 in the terminal by:
    ```bash
    ssh -p 2220 bandit3@bandit.labs.overthewire.org
    ```

2. Enter the password: `MNk8KNH3Usiio41PRUEoDFPqfxLPlSmx`

3. Enter `ls` to see what files are there:
    ```bash
    bandit3@bandit:~$ ls
    inhere
    ```
4. Do a `cd` to go to the `inhere` directory:
    ```bash
    bandit3@bandit:~$ cd inhere
    ```

5. To see if there's any hidden files, do an `ls -a`:
    ```bash
    bandit3@bandit:~/inhere$ ls -a
    .  ..  ...Hiding-From-You
    ```

6. Now `cat` the file:
    ```bash
    bandit3@bandit:~/inhere$ cat ...Hiding-From-You
    2WmrDFRmJIq3IPxneAaMGhap0pFhF3NJ
    ```
    Which is the password we're looking for.

Summary: If you `ls` in a directory, and you don't see anything, mabye there's a hidden file, so do an `ls -a` to see the hidden files.

## LEVEL 4 -> LEVEL 5

> THE PASSWORD is `4oQYVPkxZOOEOO5pTW81FB8j8lxXGUQw`

1. Log into bandit4 in the terminal by:
    ```bash
    ssh -p 2220 bandit4@bandit.labs.overthewire.org
    ```

2. Enter the password: `2WmrDFRmJIq3IPxneAaMGhap0pFhF3NJ`

3. Follow the following steps: 1. `ls`, 2. `cd inhere`, 3. `ls`
    ```bash
    bandit4@bandit:~$ ls
    inhere
    bandit4@bandit:~$ cd inhere
    bandit4@bandit:~/inhere$ ls
    -file00  -file02  -file04  -file06  -file08
    -file01  -file03  -file05  -file07  -file09
    ```

4. To instantly see all the files in one go, type in this command:

    ```bash
    cat ./-file*
    ```

    ```bash
    bandit4@bandit:~/inhere$ cat ./-file*
    N?.????9??????F??p???????tk???%???????n?Qy?y͍?{+R?bZ?k?F?*	
    l?????]?a߯-@gQ?÷?wz?P?ߠy??pӻT9?F??3ˤ????)
    T?՜F?ǭ??QĹ?M???p4?-?8??=??!#g???4oQYVPkxZOOEOO5pTW81FB8j8lxXGUQw
    ?$}P?cL???s??@?2%Y?(|?^??J
                    ы?Ϣ??
    ```
    Looking from the gibberish, it seems that the pattern for the passwords leads to `4oQYVPkxZOOEOO5pTW81FB8j8lxXGUQw`.

Summary: You can instantly see all the files by `cat`ing them with an `*`.

## LEVEL 5 -> LEVEL 6

> THE PASSWORD is `HWasnPhtq9AVKe0dmk45nxy20cvUa6EG`

1. Log into bandit5 in the terminal by:
    ```bash
    ssh -p 2220 bandit5@bandit.labs.overthewire.org
    ```

2. Enter the password: `4oQYVPkxZOOEOO5pTW81FB8j8lxXGUQw`

3. Follow the following steps: 1. `ls`, 2. `cd inhere`, 3. `ls -a`
    ```bash
    bandit5@bandit:~$ ls
    inhere
    bandit5@bandit:~$ cd inhere
    bandit5@bandit:~/inhere$ ls -a
    .            maybehere02  maybehere06  maybehere10  maybehere14  maybehere18
    ..           maybehere03  maybehere07  maybehere11  maybehere15  maybehere19
    maybehere00  maybehere04  maybehere08  maybehere12  maybehere16
    maybehere01  maybehere05  maybehere09  maybehere13  maybehere17
    ```

4. To find a human-readable; 1033 bytes in size; not executable file, we are going to use the following command: `find . -type f -readable -size 1033c ! -executable`. 
Thank you for the help [StackOverFlow](https://unix.stackexchange.com/questions/43148/unix-commands-find).

    ```bash
    bandit5@bandit:~/inhere$ find . -type f -readable -size 1033c ! -executable
    ./maybehere07/.file2
    ```

5. Go to the `maybehere07` directory and `cat` the `.file2` file:
    ```bash
    bandit5@bandit:~/inhere$ cd maybehere07
    bandit5@bandit:~/inhere/maybehere07$ ls
    -file1  -file2  -file3  spaces file1  spaces file2  spaces file3
    bandit5@bandit:~/inhere/maybehere07$ cat .file2
    HWasnPhtq9AVKe0dmk45nxy20cvUa6EG
    bandit5@bandit:~/inhere/maybehere07
    ```
Summary: You can use `find` to search up specific files that are on the directory, even if it's embedded inside lots of other directories.

## LEVEL 6 -> LEVEL 7

> THE PASSWORD is `morbNTDkSW6jIlUc0ymOdMaLnOlFVAaj`

1. Log into bandit6 in the terminal by:
    ```bash
    ssh -p 2220 bandit6@bandit.labs.overthewire.org
    ```

2. Enter the password: `HWasnPhtq9AVKe0dmk45nxy20cvUa6EG`

3. To find the directory for the password, use this command: `find / -user bandit7 -group bandit6 2>/dev/null`. Thanks Jeff.
    ```bash
    bandit6@bandit:~$ find / -user bandit7 -group bandit6 2>/dev/null
    /var/lib/dpkg/info/bandit7.password
    ```
4. Then do `cat /var/lib/dpkg/info/bandit7.password`:
    ```bash
    bandit6@bandit:~$ cat /var/lib/dpkg/info/bandit7.password
    morbNTDkSW6jIlUc0ymOdMaLnOlFVAaj
    ```
    Password found.

Summary: You can also use `find` to get the directory for files that you don't really have permission to.

## LEVEL 7 -> LEVEL 8

> THE PASSWORD is `dfwvzFQi4mU0wfNbFOe9RoWskMLg7eEc`

1. Log into bandit7 in the terminal by:
    ```bash
    ssh -p 2220 bandit7@bandit.labs.overthewire.org
    ```

2. Enter the password: `morbNTDkSW6jIlUc0ymOdMaLnOlFVAaj`

3. Type in `ls` to see what files/directories are there:
    ```bash
    bandit7@bandit:~$ ls 
    data.txt
    ```

4. Find the word next to "millionth" by using `grep`. Enter the command `cat data.txt | grep millionth`.
    ```bash
    bandit7@bandit:~$ cat data.txt | grep millionth
    millionth	dfwvzFQi4mU0wfNbFOe9RoWskMLg7eEc
    ```
Password found!

Summary: Use `grep` to find something that's in the file itself.

## LEVEL 8 -> LEVEL 9

> THE PASSWORD is `4CKMh1JI91bUIZZPXDqGanal4xvAg0JM`

1. Log into bandit8 in the terminal by:
    ```bash
    ssh -p 2220 bandit8@bandit.labs.overthewire.org
    ```

2. Enter the password: `dfwvzFQi4mU0wfNbFOe9RoWskMLg7eEc`

3. Type in `ls` to see what files/directories are there:
    ```bash
    bandit8@bandit:~$ ls 
    data.txt
    ```

4. To get the only line of text that occurs only once, we have to use `sort` and `uniq`. Enter the following command: `sort data.txt | uniq -u`
    ```bash
    bandit8@bandit:~$ sort data.txt | uniq -u
    4CKMh1JI91bUIZZPXDqGanal4xvAg0JM
    ```
Password found!

Summary: `sort [thefile.txt] | uniq -u` helps with finding the non-repeating line.

## LEVEL 9 -> LEVEL 10

> THE PASSWORD is `xX9kMYMmlN4MgbpfMiqey`

1. Log into bandit9 in the terminal by:
    ```bash
    ssh -p 2220 bandit9@bandit.labs.overthewire.org
    ```

2. Enter the password: `4CKMh1JI91bUIZZPXDqGanal4xvAg0JM`

3. Type in the command: `strings data.txt | grep ==========`.

    ```bash
    bandit9@bandit:~$ strings data.txt | grep ==========
    \a!;========== the
    ========== passwordf
    ========== isc
    ========== FGUW5ilLVJrxX9kMYMmlN4MgbpfMiqey
    ```
    Password found!

Summary: Use `strings` instead of `cat` to find human readable stuff with `grep`.

## LEVEL 10 -> LEVEL 11

> THE PASSWORD is `dtR173fZKb0RRsDFSGsg2RWnpNVj3qRr`

1. Log into bandit10 in the terminal by:
    ```bash
    ssh -p 2220 bandit10@bandit.labs.overthewire.org
    ```

2. Enter the password: `FGUW5ilLVJrxX9kMYMmlN4MgbpfMiqey`

3. Do `cat data.txt`
    ```bash
    bandit10@bandit:~$ cat data.txt
    VGhlIHBhc3N3b3JkIGlzIGR0UjE3M2ZaS2IwUlJzREZTR3NnMlJXbnBOVmozcVJyCg==
    ```

4. Use base64 to decode. Enter the command: `echo VGhlIHBhc3N3b3JkIGlzIGR0UjE3M2ZaS2IwUlJzREZTR3NnMlJXbnBOVmozcVJyCg== | base64 --decode`. Thank you [AskUbuntu](https://askubuntu.com/questions/178521/how-can-i-decode-a-base64-string-from-the-command-line).
    ```bash
    bandit10@bandit:~$ echo VGhlIHBhc3N3b3JkIGlzIGR0UjE3M2ZaS2IwUlJzREZTR3NnMlJXbnBOVmozcVJyCg== | base64 --decode
    The password is dtR173fZKb0RRsDFSGsg2RWnpNVj3qRr
    ```
    Password found!

Summary: Use `base64` to decode the encoded string.

## LEVEL 11 -> LEVEL 12

> THE PASSWORD is `7x16WNeHIi5YkIhWsfFIqoognUTyj9Q4`

1. Log into bandit11 in the terminal by:
    ```bash
    ssh -p 2220 bandit11@bandit.labs.overthewire.org
    ```

2. Enter the password: `dtR173fZKb0RRsDFSGsg2RWnpNVj3qRr`

3. When you `cat data.txt`, it will show an encrypted Rot13 line.
    ```bash
    bandit11@bandit:~$ cat data.txt
    Gur cnffjbeq vf 7k16JArUVv5LxVuJfsSVdbbtaHGlw9D4
    ```

4. To decode Rot13, use the command `cat data.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m'`
    ```bash
    bandit11@bandit:~$ cat data.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m'
    The password is 7x16WNeHIi5YkIhWsfFIqoognUTyj9Q4
    ```
    Password found!

Summary: Use `tr` to translate characters / decrypt them if they're somewhat like a Ceasar Cipher.