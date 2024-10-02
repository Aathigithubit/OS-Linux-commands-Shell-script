# OS-Linux-commands-Shell-scripting
Operating systems Lab exercise
# Linux commands-Shell scripting
Linux commands-Shell scripting

# AIM:
To practice Linux Commands and Shell Scripting

# DESIGN STEPS:

### Step 1:

Navigate to any Linux environment installed on the system or installed inside a virtual environment like virtual box/vmware or online linux JSLinux (https://bellard.org/jslinux/vm.html?url=alpine-x86.cfg&mem=192) or docker.

### Step 2:

Execute the following commands

### Step 3:

Testing the commands for the desired output. 

# COMMANDS:
### Create the following files file1, file2 as follows:
cat > file1
```
Preethi
Farhana
Zafreen
^d
```
cat > file2
```
Gayathri
Mahalakshmi
Hemavathy
^d
```
### Display the content of the files
cat < file1
## OUTPUT
```
![image](https://github.com/user-attachments/assets/126405bf-e4a3-4f37-934c-e3358c597f65)


```


cat < file2
## OUTPUT
```
![image](https://github.com/user-attachments/assets/9c7e6da7-f5a4-490a-9977-600e49054046)


```

# Comparing Files
cmp file1 file2
## OUTPUT
```
![image](https://github.com/user-attachments/assets/76fab1aa-1753-4b6e-ab84-160b9a1d58cd)

file1 file2 differ: char 1, line 1
```
comm file1 file2
 ## OUTPUT
```
![image](https://github.com/user-attachments/assets/180fea0c-5b63-47b4-88b5-d818d5513004)

 Gayathri
        Mahalakshmi
        Hemavathy
Preethi
Farhana
Zafreen
```
 
diff file1 file2
## OUTPUT
```
![image](https://github.com/user-attachments/assets/f617dafa-9dfe-4501-84ec-ded4191d08b9)

--- file1
+++ file2
@@ -1,3 +1,3 @@
-Preethi
-Farhana
-Zafreen
+Gayathri
+Mahalakshmi
+Hemavathy
```

#Filters

### Create the following files file11, file22 as follows:

cat > file11
```
Hello world
This is my world
^d
```
cat > file22
```
1001 | Ram | 10000 | HR
1002 | tom |  5000 | Admin
1003 | Joe |  7000 | Developer
^d
```


cut -c1-3 file11
## OUTPUT
```
![image](https://github.com/user-attachments/assets/e0c22548-bf88-4b4e-92ad-f37ea8b209ac)

Hel
Thi
```



cut -d "|" -f 1 file22
## OUTPUT
```
![image](https://github.com/user-attachments/assets/8483ac79-1cbd-488f-bccc-d85596fbef28)

1001
1002
1003
```


cut -d "|" -f 2 file22
## OUTPUT
```
![image](https://github.com/user-attachments/assets/f5434f30-04bb-42dc-a6e1-7f9801e53bc5)

Ram
tom
Joe
```

cat > newfile 
```
Hello world
hello world
^d
````
cat < newfile 
Hello world
hello world
 
grep Hello newfile 
## OUTPUT
```
![image](https://github.com/user-attachments/assets/1f8b11a1-7ea0-451d-9b9b-5ba7f07d187d)

Hello world
```

grep hello newfile 
## OUTPUT
```
![image](https://github.com/user-attachments/assets/cf08555e-a90c-46f7-907c-0666bfa12011)

hello world
```


grep -v hello newfile 
## OUTPUT
```
![image](https://github.com/user-attachments/assets/8a5edc23-178a-4e4f-a420-f698e0c1e576)

Hello world
```


cat newfile | grep -i "hello"
## OUTPUT
```
![image](https://github.com/user-attachments/assets/c3872d94-e171-4ce1-a93e-a9c33fe5bc9b)

Hello world
```



cat newfile | grep -i -c "hello"
## OUTPUT
```
![image](https://github.com/user-attachments/assets/bee3b024-b1a8-4b2b-8fa0-b92da9d99b01)

2
```

grep -w -n world newfile   
## OUTPUT
```
![image](https://github.com/user-attachments/assets/8e19e6b3-2567-4445-8a16-d530def9482f)

1: Hello world
2: hello world
```

cat < newfile 
```
Hello world
hello world
Linux is world number 1
Unix is predecessor
Linux is best in this World
^d
```

cat > newfile
```
Hello world
hello world
Linux is world number 1
Unix is predecessor
Linux is best in this World
^d
 ```
egrep -w 'Hello|hello' newfile 
## OUTPUT
```
![image](https://github.com/user-attachments/assets/3ecc377a-037d-47a4-bc62-7cacaabfb412)

Hello world
hello world
```


egrep -w '(H|h)ello' newfile 
## OUTPUT
```
![image](https://github.com/user-attachments/assets/e21c9c6d-7dd5-486a-a559-12e0b2a67a1f)

Hello world
hello world
```


egrep -w '(H|h)ell[a-z]' newfile 
## OUTPUT
```
![image](https://github.com/user-attachments/assets/17bdd12e-76e5-4f4a-984f-ac0ad1054de2)

Hello world
hello world
```



egrep '(^hello)' newfile 
## OUTPUT

```
![image](https://github.com/user-attachments/assets/1646acda-9673-4ee5-8b75-9c344cca8867)

hello world
```

egrep '(world$)' newfile 
## OUTPUT
```
![image](https://github.com/user-attachments/assets/8e96c3df-9037-4b7b-b15d-bbd9f3215041)

Hello world
hello world
```


egrep '(World$)' newfile 
## OUTPUT
```
![image](https://github.com/user-attachments/assets/a9760e24-fc70-4e32-a53a-6e20e3414480)

Linux is best in this World
```

egrep '((W|w)orld$)' newfile 
## OUTPUT
```
![image](https://github.com/user-attachments/assets/05e92754-8fb0-4a01-a630-f81510dda141)

Hello world
hello world
Linux is best in this World
```


egrep '[1-9]' newfile 
## OUTPUT
```
![image](https://github.com/user-attachments/assets/adec6185-751a-40e9-b0d5-aba5d14e5668)

Linux is world number 1
```


egrep 'Linux.*world' newfile 
## OUTPUT
```
![image](https://github.com/user-attachments/assets/f6359515-d9f9-483c-9610-bb65a744b082)

Linux is world number 1
```

egrep 'Linux.*World' newfile 
## OUTPUT
```
![image](https://github.com/user-attachments/assets/91e3bdb3-cf7b-4de8-9191-1ed5c15887f2)

Linux is best in this World
```

egrep l{2} newfile
## OUTPUT
```
![image](https://github.com/user-attachments/assets/5a124db6-ecbe-439c-a7e9-4c01db4459c1)

Hello world
hello world
```


egrep 's{1,2}' newfile
## OUTPUT 
```
![image](https://github.com/user-attachments/assets/dcca40cb-aa24-4496-8411-8de0be815b5d)

Linux is world number 1
Unix is predecessor
Linux is best in this World
```

cat > file23
```
1001 | Ram | 10000 | HR
1001 | Ram | 10000 | HR
1002 | tom |  5000 | Admin
1003 | Joe |  7000 | Developer
1005 | Sam |  5000 | HR
1004 | Sit |  7000 | Dev
1003 | Joe |  7000 | Developer
1001 | Ram | 10000 | HR
^d
```


sed -n -e '3p' file23
## OUTPUT
```
![image](https://github.com/user-attachments/assets/ca18cd9f-f47e-437b-81b0-e65108b1da57)

1002 | tom |  5000 | Admin
```


sed -n -e '$p' file23
## OUTPUT
```
![image](https://github.com/user-attachments/assets/6768caa8-0c5e-4609-baf5-80a07b0e6df6)

1001 | Ram | 10000 | HR
```


sed  -e 's/Ram/Sit/' file23
## OUTPUT
```
![image](https://github.com/user-attachments/assets/512bfa96-9d9f-4e6a-aaed-feb6c09b2bc2)

1001 | Sit | 10000 | HR
1001 | Sit | 10000 | HR
1002 | tom |  5000 | Admin
1003 | Joe |  7000 | Developer
1005 | Sam |  5000 | HR
1004 | Sit |  7000 | Dev
1003 | Joe |  7000 | Developer
1001 | Sit | 10000 | HR
```

sed  -e '2s/Ram/Sit/' file23
## OUTPUT
```
![image](https://github.com/user-attachments/assets/10f7a0d8-a287-428a-9f96-0fd2df6693ba)

1001 | Ram | 10000 | HR
1001 | Sit | 10000 | HR
1002 | tom |  5000 | Admin
1003 | Joe |  7000 | Developer
1005 | Sam |  5000 | HR
1004 | Sit |  7000 | Dev
1003 | Joe |  7000 | Developer
1001 | Ram | 10000 | HR
```


sed  '/tom/s/5000/6000/' file23
## OUTPUT
```
![image](https://github.com/user-attachments/assets/e4e6ae95-76c7-496a-b9ce-7e7e5a58e8a0)

1001 | Ram | 10000 | HR
1001 | Ram | 10000 | HR
1002 | tom |  6000 | Admin
1003 | Joe |  7000 | Developer
1005 | Sam |  5000 | HR
1004 | Sit |  7000 | Dev
1003 | Joe |  7000 | Developer
1001 | Ram | 10000 | HR
```


sed -n -e '1,5p' file23
## OUTPUT
```
![image](https://github.com/user-attachments/assets/8511c9f3-e12a-4aee-b58a-87340e110f59)

1001 | Ram | 10000 | HR
1001 | Ram | 10000 | HR
1002 | tom |  5000 | Admin
1003 | Joe |  7000 | Developer
1005 | Sam |  5000 | HR
```


sed -n -e '2,/Joe/p' file23
## OUTPUT
```
![image](https://github.com/user-attachments/assets/c909e5c3-a26f-4574-a3ff-a5469b4ab3c6)

1001 | Ram | 10000 | HR
1002 | tom |  5000 | Admin
1003 | Joe |  7000 | Developer
```



sed -n -e '/tom/,/Joe/p' file23
## OUTPUT
```
![image](https://github.com/user-attachments/assets/776d6e09-e76f-440f-8f48-8e169924ec50)

1002 | tom |  5000 | Admin
1003 | Joe |  7000 | Developer
```


seq 10 
## OUTPUT
```
![image](https://github.com/user-attachments/assets/bee77282-4b8b-4ada-aa42-6b3a6e4d457c)

1
2
3
4
5
6
7
8
9
10
```


seq 10 | sed -n '4,6p'
## OUTPUT
```
![image](https://github.com/user-attachments/assets/8b06be84-eaa0-4c2c-87f2-6a83c0e271d5)

4
5
6
```


seq 10 | sed -n '2,~4p'
## OUTPUT
```
![image](https://github.com/user-attachments/assets/ebf638c1-bb2f-48e6-b65d-3451fddd9ee8)

sed: no address after comma
```


seq 3 | sed '2a hello'
## OUTPUT
```
![image](https://github.com/user-attachments/assets/286c3fd5-6af3-4637-865c-3f319bd6c2cc)

1
2
hello
3
```


seq 2 | sed '2i hello'
## OUTPUT
```
![image](https://github.com/user-attachments/assets/a3ca4224-cb5c-4c84-b014-779d0b45fcfd)

1
hello
2
```

seq 10 | sed '2,9c hello'
## OUTPUT
```
![image](https://github.com/user-attachments/assets/ff35ba6c-fa5b-447c-9841-31aeebad6290)

1
hello 10
```

sed -n '2,4{s/^/$/;p}' file23
## OUTPUT
```
![image](https://github.com/user-attachments/assets/726d8a61-1964-453a-96e5-6d9c253ed3ea)

$1001 | Ram | 10000 | HR
$1002 | tom |  5000 | Admin
$1003 | Joe |  7000 | Developer
```


sed -n '2,4{s/$/*/;p}' file23
## OUTPUT
```
![image](https://github.com/user-attachments/assets/0e2221fc-b790-4e29-a4d7-814cf323d372)

1001 | Ram | 10000 | HR*
1002 | tom |  5000 | Admin*
1003 | Joe |  7000 | Developer*
```

#Sorting File content
cat > file21
```
1001 | Ram | 10000 | HR
1002 | tom |  5000 | Admin
1003 | Joe |  7000 | Developer
1005 | Sam |  5000 | HR
1004 | Sit |  7000 | Dev
``` 
sort file21
## OUTPUT
```
![image](https://github.com/user-attachments/assets/3bb9860a-bd0f-4fb7-bfe7-5bc2e6c70564)

1001 | Ram | 10000 | HR
1002 | tom |  5000 | Admin
1003 | Joe |  7000 | Developer
1004 | Sit |  7000 | Dev
1005 | Sam |  5000 | HR

```

cat > file22
```
1001 | Ram | 10000 | HR
1001 | Ram | 10000 | HR
1002 | tom |  5000 | Admin
1003 | Joe |  7000 | Developer
1005 | Sam |  5000 | HR
1004 | Sit |  7000 | Dev
``` 
uniq file22
## OUTPUT
```
![image](https://github.com/user-attachments/assets/95c79498-4ddd-481a-a62f-a0217ea7678e)

1001 | Ram | 10000 | HR
1002 | tom |  5000 | Admin
1003 | Joe |  7000 | Developer
1005 | Sam |  5000 | HR
1004 | Sit |  7000 | Dev
```


#Using tr command
cat file23 | tr [:lower:] [:upper:]
 
## OUTPUT
```
![image](https://github.com/user-attachments/assets/7859eb8e-392e-4a37-9b7e-2b30476bb725)

1001 | RAM | 10000 | HR
1001 | RAM | 10000 | HR
1002 | TOM |  5000 | ADMIN
1003 | JOE |  7000 | DEVELOPER
1005 | SAM |  5000 | HR
1004 | SIT |  7000 | DEV
1003 | JOE |  7000 | DEVELOPER
1001 | RAM | 10000 | HR

```

cat < urllist.txt
```
www. yahoo. com
www. google. com
www. mrcet.... com
^d
 ```
cat > urllist.txt
```
www. yahoo. com
www. google. com
www. mrcet.... com
 ```
cat urllist.txt | tr -d ' '
 ## OUTPUT
```
![image](https://github.com/user-attachments/assets/cf786828-9cb9-43a2-b3e7-5628a3b05a91)

www.yahoo.com
www.google.com
www.mrcet....com
```

cat urllist.txt | tr -d ' ' | tr -s '.'
## OUTPUT
```
![image](https://github.com/user-attachments/assets/6b6e4ad9-fe85-465f-9a4a-dc338610f8e1)

www.yahoo.com
www.google.com
www.mrcet.com
```


#Backup commands
tar -cvf backup.tar *
## OUTPUT
```
![image](https://github.com/user-attachments/assets/25ce1107-eda0-4fed-8382-2129999c774e)

bench.py
file
file1
file11
file2
file21
file22
file23
hello.c
hello.js
newfile
readme.txt
urllist.txt
```

mkdir backupdir
 
mv backup.tar backupdir
 
tar -tvf backup.tar
## OUTPUT
```
![image](https://github.com/user-attachments/assets/913ebc82-b6c0-4bf8-a4ef-1f72acace490)

-rw-r--r-- root/root       114 2020-07-05 23:17:07 bench.py
-rw-r--r-- root/root         0 2024-02-21 13:41:13 file
-rw-r--r-- root/root        24 2024-02-21 13:28:46 file1
-rw-r--r-- root/root        29 2024-02-21 13:32:34 file11
-rw-r--r-- root/root        31 2024-02-21 13:29:10 file2
-rw-r--r-- root/root       131 2024-02-21 15:53:13 file21
-rw-r--r-- root/root       155 2024-02-21 15:54:56 file22
-rw-r--r-- root/root       210 2024-02-21 21:18:35 file23
-rw-r--r-- root/root        76 2020-07-03 14:45:56 hello.c
-rw-r--r-- root/root        22 2020-06-26 14:57:33 hello.js
-rw-r--r-- root/root        96 2024-02-21 21:09:36 newfile
-rw-r--r-- root/root       151 2020-07-05 23:19:13 readme.txt
-rw-r--r-- root/root        52 2024-02-21 21:21:17 urllist.txt
```

tar -xvf backup.tar
## OUTPUT
```
![image](https://github.com/user-attachments/assets/ecce8e56-3dd9-4f7c-8199-0f5ca1bf05a8)

localhost:~# tar -xvf backup.tar
bench.py
file
file1
file11
file2
file21
file22
file23
hello.c
hello.js
newfile
readme.txt
urllist.txt
```
gzip backup.tar

ls .gz
## OUTPUT
```
![image](https://github.com/user-attachments/assets/8978a59d-ff83-412c-9392-dc96d1e85126)

backup.tar.gz  bench.py       hello.c        hello.js       readme.txt
```
gunzip backup.tar.gz
## OUTPUT
```
![image](https://github.com/user-attachments/assets/3fb4df55-2be3-4687-bcc4-72de80649e02)

bench.py
hello.c
hello.js
readme.txt
```
 
# Shell Script
```
echo '#!/bin/sh' > my-script.sh
echo 'echo Hello World‘; exit 0 >> my-script.sh
```
chmod 755 my-script.sh
./my-script.sh
## OUTPUT
```
![image](https://github.com/user-attachments/assets/fa16a921-792d-4d5c-8db5-95b29f0bfacf)

Hello World
```
 
cat << stop > herecheck.txt
```
hello in this world
i cant stop
for this non stop movement
stop
```

cat herecheck.txt
## OUTPUT
```
![image](https://github.com/user-attachments/assets/7481fd62-356a-40c4-b8e3-05113c34b463)

hello in this world
i cant stop
for this non stop movement
```

cat < scriptest.sh 
```bash
\#!/bin/sh
echo “File name is $0 ”
echo "File name is " `basename $0`
echo “First arg. is ” $1
echo “Second arg. is ” $2
echo “Third arg. is ” $3
echo “Fourth arg. is ” $4
echo 'The $@ is ' $@
echo 'The $\# is ' $1#
echo 'The $$ is ' $$
ps
^d
 ```

cat scriptest.sh 
```bash
\#!/bin/sh
echo “File name is $0 ”
echo "File name is " `basename $0`
echo “First arg. is ” $1
echo “Second arg. is ” $2
echo “Third arg. is ” $3
echo “Fourth arg. is ” $4
echo 'The $@ is ' $@
echo 'The $\# is ' $\#
echo 'The $$ is ' $$
ps
```
 
chmod 777 scriptest.sh
 
./scriptest.sh 1 2 3

## OUTPUT
```
![image](https://github.com/user-attachments/assets/60a2ab83-8cc4-4649-9e39-49878c429e2a)

“File name is ./scriptest.sh ”
File name is  scriptest.sh
“First arg. is ” 1
“Second arg. is ” 2
“Third arg. is ” 3
“Fourth arg. is ”
The $@ is  1 2 3
The $\# is  1#
The $$ is  5564
    PID TTY          TIME CMD
   5406 pts/0    00:00:00 bash
   5471 pts/0    00:00:00 bash
   5564 pts/0    00:00:00 bash
   5576 pts/0    00:00:00 ps
```
 
ls file1
## OUTPUT
```
![image](https://github.com/user-attachments/assets/8b9757c6-6f0c-4663-950c-dd76cc6360bd)

file1  file2  file3
```
echo $?
## OUTPUT 
```
![image](https://github.com/user-attachments/assets/adf02f12-32ed-4f3e-913d-0bec4227256a)

0
```
./one bash: ./one: Permission denied
## OUTPUT
```
![image](https://github.com/user-attachments/assets/dfc2900a-e75b-4d47-8af0-d78c63f3df3e)

126
```
abcd echo $?
## OUTPUT
```
![image](https://github.com/user-attachments/assets/99de6cd8-a12d-4e87-b201-873a8f42c835)

127
```


 
# mis-using string comparisons

cat < strcomp.sh 
```bash
\#!/bin/bash
val1=baseball
val2=hockey
if [ $val1 \> $val2 ]
then
echo "$val1 is greater than $val2"
else
echo "$val1 is less than $val2"
fi
^d
```

cat strcomp.sh 
```bash
\#!/bin/bash
val1=baseball
val2=hockey
if [ $val1 \> $val2 ]
then
echo "$val1 is greater than $val2"
else
echo "$val1 is less than $val2"
fi
```
chmod 755 strcomp.sh
 
./strcomp.sh 
## OUTPUT
```
![image](https://github.com/user-attachments/assets/c064293a-d958-4340-834e-b8d2fffe8c46)

baseball is less than hockey
```


# check file ownership
cat < psswdperm.sh 
```bash
\#!/bin/bash
if [ -O /etc/passwd ]
then
echo “You are the owner of the /etc/passwd file”
else
echo “Sorry, you are not the owner of the /etc/passwd file”
fi
^d
```

cat psswdperm.sh 
```bash

/#!/bin/bash
if [ -O /etc/passwd ]
then
echo “You are the owner of the /etc/passwd file”
else
echo “Sorry, you are not the owner of the /etc/passwd file”
fi
 ```
./psswdperm.sh
## OUTPUT
```
![image](https://github.com/user-attachments/assets/323c2c35-f0ef-4fa2-b53f-76c13cef2d14)

Sorry, you are not the owner of the /etc/passwd file
```

# check if with file location
cat>ifnested.sh 
```bash
\#!/bin/bash
if [ -e $HOME ]
then
echo “$HOME The object exists, is it a file?”
if [ -f $HOME ]
then
echo “Yes,$HOME it is a file!”
else
echo “No,$HOME it is not a file!”
if [ -f $HOME/.bash_history ]
then
echo “But $HOME/.bash_history is a file!”
fi
fi
else
echo “Sorry, the object does not exist”
fi
^d
```
cat ifnested.sh 
```
\#!/bin/bash
if [ -e $HOME ]
then
echo “$HOME The object exists, is it a file?”
if [ -f $HOME ]
then
echo “Yes,$HOME it is a file!”
else
echo “No,$HOME it is not a file!”
if [ -f $HOME/.bash_history ]
then
echo “But $HOME/.bash_history is a file!”
fi
fi
else
echo “Sorry, the object does not exist”
fi
```

./ifnested.sh 
## OUTPUT
```
![image](https://github.com/user-attachments/assets/8781bdbc-fbca-44e9-afef-48c94efa1126)

![image](https://github.com/user-attachments/assets/5b5ce97c-fcd3-4051-9df8-c6d5c4403a76)

“/home/sec The object exists, is it a file?”
“No,/home/sec it is not a file!”
“But /home/sec/.bash_history is a file!”
```



# using numeric test comparisons
cat > iftest.sh 
```bash
\#!/bin/bash
val1=10
val2=11
if [ $val1 -gt 5 ]
then
echo “The test value $val1 is greater than 5”
fi
if [ $val1 -eq $val2 ]
then
echo “The values are equal”
else
echo “The values are different”
fi
^d
```


cat iftest.sh 
```bash
\#!/bin/bash
val1=10
val2=11
if [ $val1 -gt 5 ]
then
echo “The test value $val1 is greater than 5”
fi
if [ $val1 -eq $val2 ]
then
echo “The values are equal”
else
echo “The values are different”
fi
```

$ chmod 755 iftest.sh
 
$ ./iftest.sh 
## OUTPUT
```
![image](https://github.com/user-attachments/assets/48550bf9-3fde-4b36-b0be-d254eb96b31f)

“The test value 10 is greater than 5”
“The values are different”
```


# check if a file
cat > ifnested.sh 
```bash
\#!/bin/bash
if [ -e $HOME ]
then
echo “$HOME The object exists, is it a file?”
if [ -f $HOME ]
then
echo “Yes,$HOME it is a file!”
else
echo “No,$HOME it is not a file!”
if [ -f $HOME/.bash_history ]
then
echo “But $HOME/.bash_history is a file!”
fi
fi
else
echo “Sorry, the object does not exist”
fi
^d
```

cat ifnested.sh 
```bash
\#!/bin/bash
if [ -e $HOME ]
then
echo “$HOME The object exists, is it a file?”
if [ -f $HOME ]
then
echo “Yes,$HOME it is a file!”
else
echo “No,$HOME it is not a file!”
if [ -f $HOME/.bash_history ]
then
echo “But $HOME/.bash_history is a file!”
fi
fi
else
echo “Sorry, the object does not exist”
fi
```

$ chmod 755 ifnested.sh
 
$ ./ifnested.sh 
## OUTPUT
```
![image](https://github.com/user-attachments/assets/df2455d3-ecad-431e-81fb-c7eb20e82298)

“/home/sec The object exists, is it a file?”
“No,/home/sec it is not a file!”
“But /home/sec/.bash_history is a file!”
```

# looking for a possible value using elif
cat elifcheck.sh 
```bash
\#!/bin/bash
if [ $USER = Ram ]
then
echo "Welcome $USER"
echo "Please enjoy your visit"
elif [ $USER = Rahim ]
then
echo "Welcome $USER"
echo "Please enjoy your visit"
elif [ $USER = Robert ]
then
echo "Special testing account"
elif [ $USER = gganesh ]
then
echo "$USER, Do not forget to logout when you're done"
else
echo "Sorry, you are not allowed here"
fi
```

$ chmod 755 elifcheck.sh
 
$ ./elifcheck.sh 
## OUTPUT
```
![image](https://github.com/user-attachments/assets/b0d1ea96-420d-4673-a2f6-814747cd0945)

Sorry, you are not allowed here
```


# testing compound comparisons
cat> ifcompound.sh 
```bash
\#!/bin/bash
if [ -d $HOME ] && [ -w $HOME ]
then
echo "The file exists and you can write to it"
else
echo "I cannot write to the file"
fi
```
$ chmod 755 ifcompound.sh
$ ./ifcompound.sh 
## OUTPUT
```
![image](https://github.com/user-attachments/assets/58fed3dc-66d2-4b83-aba2-4c5d84e4b55f)

The file exists and you can write to it
```

# using the case command
cat >casecheck.sh 
```bash
case $USER in
Ram | Robert)
echo "Welcome, $USER"
echo "Please enjoy your visit";;
Rahim)
echo "Special testing account";;
gganesh)
echo "$USER, Do not forget to log off when you're done";;
*)
echo "Sorry, you are not allowed here";;
esac
```
$ chmod 755 casecheck.sh 
 
$ ./casecheck.sh
## OUTPUT
```
![image](https://github.com/user-attachments/assets/e20a1664-ac8f-4bc5-8502-05358097ec1f)

Sorry, you are not allowed here
```
 
cat > whiletest
```bash
#!/bin/bash
#while command test
var1=10
while [ $var1 -gt 0 ]
do
echo $var1
var1=$[ $var1 - 1 ]
done
```
$ chmod 755 whiletest.sh
 
$ ./whiletest.sh
## OUTPUT
```
10
9
8
7
6
5
4
3
2
1
```
 
 
cat untiltest.sh 
```bash
\#using the until command
var1=100
until [ $var1 -eq 0 ]
do
echo $var1
var1=$[ $var1 - 25 ]
done
``` 
$ chmod 755 untiltest.sh
## OUTPUT
```
100
75
50
25
```
 
 
 
cat forin1.sh 
```bash
\#!/bin/bash
\#basic for command
for test in Alabama Alaska Arizona Arkansas California Colorado
do
echo The next state is $test
done
 ```
 
$ chmod 755 forin1.sh
## OUTPUT
```
![image](https://github.com/user-attachments/assets/1c7e4420-c2a4-457d-94fd-2a9fed987d5f)

The next state is Alabama
The next state is Alaska
The next state is Arizona
The next state is Arkansas
The next state is California
The next state is Colorado
```
 
 
cat forin2.sh 
```bash
\#!/bin/bash
\# another example of how not to use the for command
for test in I don't know if this'll work
do
echo “word:$test”
done
 ```
 
$ chmod 755 forin2.sh $ ./forin2.sh
## OUTPUT
```
![image](https://github.com/user-attachments/assets/bdfe52fb-cd3d-4c3d-9c8a-b8fd3e16c825)

“word:I”
“word:dont know if thisll”
“word:work”
```
cat forin3.sh 
```bash
\#!/bin/bash
\# another example of how not to use the for command
for test in I don\'t know if "this'll" work
do
echo "word:$test"
done
```
$ ./forin3.sh
## OUTPUT
```
![image](https://github.com/user-attachments/assets/2d31bdb7-59a2-458c-bfb5-8d6249e85d6b)

word:I
word:don't
word:know
word:if
word:this'll
word:work
```
 
cat forin1.sh 
```bash
#!/bin/bash
# basic for command
for test in Alabama Alaska Arizona Arkansas California Colorado
do
echo The next state is $test
done
```
$ chmod 755 forin1.sh
## OUTPUT
```The next state is Alabama
![image](https://github.com/user-attachments/assets/7c356ae9-c5b0-47a6-b940-b0bf76972f48)

The next state is Alaska
The next state is Arizona
The next state is Arkansas
The next state is California
The next state is Colorado
```

cat forinfile.sh 
```bash
#!/bin/bash
# reading values from a file
file="cities"
for state in `cat $file`
do
echo "Visit beautiful $file“
done
```
$ chmod 777 forinfile.sh
$ cat cities
Hyderabad
Alampur
Basara
Warangal
Adilabad
Bhadrachalam
Khammam

## OUTPUT
```
![image](https://github.com/user-attachments/assets/abdfa786-d857-4ca7-a04d-7b8af353b3f8)

Visit beautiful Hyderabad
Visit beautiful Alampur
Visit beautiful Basara
Visit beautiful Warangal
Visit beautiful Adilabad
Visit beautiful Bhadrachalam
Visit beautiful Khammam
```


cat forctype.sh 
```bash
#!/bin/bash
# testing the C-style for loop
for (( i=1; i <= 5; i++ ))
do
echo "The value of i is $i"
done
````
$ chmod 755 forctype.sh
$ ./forctype.sh 
## OUTPUT
```
![image](https://github.com/user-attachments/assets/135f90ce-2ee9-4e32-8034-d5294890eb0c)

The value of i is 1
The value of i is 2
The value of i is 3
The value of i is 4
The value of i is 5
```

cat forctype1.sh 
```bash
#!/bin/bash
# multiple variables
for (( a=1, b=5; a <= 5; a++, b-- ))
do
echo "$a - $b"
done
```
$ chmod 755 forctype.sh
$ ./forctype1.sh 
## OUTPUT
```
![image](https://github.com/user-attachments/assets/8c0f8326-78b4-4497-aa58-e46e86535ab2)

1 - 5
2 - 4
3 - 3
4 - 2
5 - 1
```

cat fornested1.sh 
```bash
#!/bin/bash
# nesting for loops
for (( a = 1; a <= 3; a++ ))
do
echo "Starting loop $a:"
for (( b = 1; b <= 3; b++ ))
do
echo " Inside loop: $b"
done
done
```
$ chmod 755 fornested1.sh
 
$ ./fornested1.sh 
 ## OUTPUT
 ```
![image](https://github.com/user-attachments/assets/222aaeac-a95d-44a3-b8ef-c3ebc162d198)

 Starting loop 1:
 Inside loop: 1
 Inside loop: 2
 Inside loop: 3
Starting loop 2:
 Inside loop: 1
 Inside loop: 2
 Inside loop: 3
Starting loop 3:
 Inside loop: 1
 Inside loop: 2
 Inside loop: 3
```

 
cat forbreak.sh 
```bash
#!/bin/bash
# breaking out of a for loop
for var1 in 1 2 3 4 5
do
if [ $var1 -eq 3 ]
then
break
fi
echo "Iteration number: $var1"
done
echo "The for loop is completed“
```
$ chmod 755 forbreak.sh
 
$ ./forbreak.sh 
## OUTPUT
```
![image](https://github.com/user-attachments/assets/e8268e77-6593-4760-b642-97bba93b793f)

Iteration number: 1
Iteration number: 2
The for loop is completed
```
 
cat forbreak.sh 
```bash
#!/bin/bash
# breaking out of a for loop
for var1 in 1 2 3 4 5
do
if [ $var1 -eq 3 ]
then
continue
fi
echo "Iteration number: $var1"
done
echo "The for loop is completed“
```

 
$ chmod 755 forcontinue.sh
 
$ ./forcontinue.sh 
## OUTPUT
```
![image](https://github.com/user-attachments/assets/334efb35-130c-49c6-a904-40d244597d04)

Iteration number: 1
Iteration number: 2
Iteration number: 4
Iteration number: 5
The for loop is completed
```
 
cat exread.sh 
```bash
#!/bin/bash
# testing the read command
echo -n "Enter your name: "
read name
echo "Hello $name, welcome to my program. "
 ```
 
$ chmod 755 exread.sh 
 
$ ./exread.sh 
## OUTPUT
```
![image](https://github.com/user-attachments/assets/1e84d52c-2ee7-4737-8445-2ea2870f556a)

Enter your name: preethi
Hello preethi, welcome to my program.

```


 cat exread1.sh
```bash
#!/bin/bash
# testing the read command
read -p "Enter your name: " name
echo "Hello $name, welcome to my program. “
``` 
$ chmod 755 exread1.sh 
$ ./exread1.sh

## OUTPUT
```
![image](https://github.com/user-attachments/assets/a0dcee45-566b-41d2-9e21-00902b5893c2)

Enter your name: preethi
Hello preethi, welcome to my program.
```
cat funcex.sh
```bash
#!/bin/bash
# trying to access script parameters inside a function
function func {
echo $[ $1 * $2 ]
}
if [ $# -eq 2 ]
then
value=`func $1 $2`
echo "The result is $value"
else
echo "Usage: badtest1 a b"
fi
```
./funcex.sh 
./funcex.sh 1 2
## OUTPUT
```
![image](https://github.com/user-attachments/assets/809d1f2c-06a1-4383-8e54-ab2eb6bc138e)
![image](https://github.com/user-attachments/assets/60f070e7-915a-4551-810c-14948da065e5)



The result is 2
```

 
cat argshift.sh
```bash
#!/bin/bash 
 while (( "$#" )); do 
  echo $1 
  shift 
done
```
$ chmod 777 argshift.sh
$ ./argshift.sh 1 2 3
## OUTPUT
```
![image](https://github.com/user-attachments/assets/bd124ea5-827e-4a60-a9cf-05c3c671b5b4)

1
2
3
```

 
 cat argshift1.sh
```bash
 #/bin/bash 
 # store arguments in a special array 
args=("$@") 
# get number of elements 
ELEMENTS=${#args[@]} 
 # echo each element in array  
# for loop 
for (( i=0;i<$ELEMENTS;i++)); do 
    echo ${args[${i}]} 
done
```
$ chmod 777 argshift.sh
$ ./argshift.sh 1 2 3
## OUTPUT
```
![image](https://github.com/user-attachments/assets/15159bdf-030a-4b96-b6f0-6f1ecaa1a362)

1
2
3
```
 
cat argshift.sh
```bash
#!/bin/bash 
set -x 
while (( "$#" )); do 
  echo $1 
  shift 
done
set +x
```
./argshift.sh 1 2 3
## OUTPUT
```
![image](https://github.com/user-attachments/assets/7d406d44-73d4-47d3-8ad1-c2d7b3d65aa9)

++ ((  3  ))
++ echo 1
1
++ shift
++ ((  2  ))
++ echo 2
2
++ shift
++ ((  1  ))
++ echo 3
3
++ shift
++ ((  0  ))
++ set +x
```
 
 
cat > nc.awk
```bash
BEGIN{}
{
print len=length($0),"\t",$0 
wordcount+=NF
chrcnt+=len
}
END {
print "total characters",chrcnt 
print "Number of Lines are",NR
print "No of Words count:",wordcount
}
 ```
cat>data.dat
```bash
bcdfghj
abcdfghj
bcdfghj
ebcdfghj
bcdfghj
ibcdfghj
bcdfghj
obcdfghj
bcdfghj
ubcdfghj
```
awk -f nc.awk data.dat
## OUTPUT 
```
![image](https://github.com/user-attachments/assets/bc107899-1522-42e0-a2b7-a024c9ef39a6)

4 	 bash
7 	 bcdfghj
8 	 abcdfghj
7 	 bcdfghj
8 	 ebcdfghj
7 	 bcdfghj
8 	 ibcdfghj
7 	 bcdfghj
8 	 obcdfghj
7 	 bcdfghj
8 	 ubcdfghj
total characters 79
Number of Lines are 11
No of Words count: 11
```
 
cat > palindrome.sh
```bash
#num=545
echo "Enter the number"
read num
s=0
rev=""
temp=$num
while [ $num -gt 0 ]
do
	# Get Remainder
	s=$(( $num % 10 ))
	# Get next digit
	num=$(( $num / 10 ))
	# Store previous number and
	# current digit in reverse
	rev=$( echo ${rev}${s} )
done
if [ $temp -eq $rev ];
then
	echo "Number is palindrome"
else
	echo "Number is NOT palindrome"
fi
```
## OUTPUT 
```
![image](https://github.com/user-attachments/assets/556d5cde-2ce5-45bf-b65a-8d3584f6aca3)

Enter the number
5
Number is palindrome
```


# RESULT:
The Commands are executed successfully.
