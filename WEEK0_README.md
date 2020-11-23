
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
