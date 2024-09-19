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

1. Log into bandit2 in the terminal by:
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

1. Log into bandit2 in the terminal by:
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

1. Log into bandit2 in the terminal by:
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

> THE PASSWORD is ``

1. Log into bandit2 in the terminal by:
    ```bash
    ssh -p 2220 bandit6@bandit.labs.overthewire.org
    ```

2. Enter the password: `HWasnPhtq9AVKe0dmk45nxy20cvUa6EG`

3. Follow the following steps: 1. `ls`, 2. `cd inhere
