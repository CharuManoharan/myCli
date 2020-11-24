
#### Command Line

1.  List how many files (hidden files included) are there in your home directory<br>
ls -lA | egrep '^d'|wc -l

2.  List how many directories (hidden dirs included) are there in your home directory<br>
ls -lA | egrep '^d'|wc -l 

3.  List all files/directories starting with letter “D” in your home directory<br>
 ls | grep '^D'

4.  Change permissions to a text file by giving read-write access to owners and groups only.<br>
 chmod 660 fileName.txt
 
5.  Find out which processes are taking up maximum CPU<br>
ps u | sort -k 1 -r | head -5

6.  Find out which processes are taking up more memory<br>
ps aux| sort -rnk 4

7.  Copy a text file from home directory to “tmp” directory<br>
cp Data.txt D:/tmp

8.  Given a text file, employee.txt, find out the following<br>
a.  List all employee ids, names and role whose name starts with “J”<br>
awk '/J/{print $1,$2,$3}' employee.txt


b.  List all fields, sorted by name in ascending order whose department is “Technology” and write them into emp.txt<br>
awk '/Technology/{print}' employee.txt | sort -d -k 2 >emp.txt

c.  List name and salaries of employees who work in “Technology” department as a “Sysadmin” and overwrite emp.txt<br>
 awk '{if($3=="Sysadmin" && $4=="Technology") print $2 $5}' employee.txt

d.  Calculate the average salary of all employees<br>
awk '{ total += $5; count++ } END { print total/count }' employee.txt

e.  List the distinct departments in the organisation.<br>
 cat employee.txt | awk '{print $4}' | sort -u

f.  Count the number of employees who are developers<br>
awk ' BEGIN {count=0} { 
 if($3=="Developer")  count++;
 } END { 
 print count 
} ' employee.txt


g. Print the distinct salaries of employees without $ sign<br>
cat employee.txt| awk '{gsub(/\.\/|\$/,"")1;print $5}'|sort -u

**OS:**
1. Find out how to determine the OS architecture? (Is it 32 bit or 64 bit)
arch
2. How to shutdown the OS from the command line.
shutdown -h

3. Find out what shell you are using.
 ps -p $$
 
4. Find out which processes are taking more memory from the command line ?
ps aux| sort -rnk 4

5. How do you terminate one process from the command line ?

Step1: Obtain the process id using below cmd
ps -fu user

Step2: kill [signal-number] pid

Step 3:  Verify the process has been terminated using 
pgrep pid


6. What is a symlink ? And how do you create one ?
A symbolic link (or "symlink") is file system feature that can be used to create a link to a specific file or folder. 
It is similar to a Windows "shortcut" or Mac "alias," but is not an actual file. Instead, a symbolic link is a entry in a file system that points to a directory or file.

ln -s <target file> <name of the link>

**Networking:**
Learn the following commands(in linux) and their respectives uses
1. ping.  
send ICMP ECHO_REQUEST packets to network hosts

2. nslookup.
query Internet name servers interactively

3. command to find ip address and mac id of the interface
ipconfig

f4. find the hostname of the machine.
hostname

