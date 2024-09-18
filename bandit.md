# Jeremy Gautama

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

> THE PASSWORD is ``

1. Log into bandit2 in the terminal by:
    ```bash
    ssh -p 2220 bandit2@bandit.labs.overthewire.org
    ```

2. Enter the password: `263JGJPfgU6LtdEvgfWU1XP5yac29mFx`
