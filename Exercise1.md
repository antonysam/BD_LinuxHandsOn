## 1) Goto /home/hduser directory and Create 2 files namely cust1.txt and cust2.txt with the first 10 lines copied from /home/hduser/hive/data/custs and last 10 lines copied from /home/hduser/hive/data/custs.
```
cd /home/hduser or ~
> /hive/data/custs
      provide some data in the cust.txt
head -10 cust.txt | tail -10 cust.txt > cust1.txt
head -10 cust.txt | tail -10 cust.txt > cust2.txt
```
## 2)Create a file namely samplefile.txt using vi editor
```
vi samplefile.txt
```
a. Type/copy 10 lines of some content
Note: Use shift in key with copy and paste
```
ctrl+c
ctrl+shift+v 
```
b. Goto line 5 and remove line 5 to 7 using command.
```
:5
dd
dd
dd
```
c. Goto last line and copy last line to first line and delete the last line manually.
```
shift+g
ctrl+shift+c
ctrl+shift+v in first line
shift+g
dd
```
d. Find for a particular word inside the file
```
:/sam
```
e. Undo the last action you did
```
ctrl+u
```
f. Save and quit the file
```
:wq
```
g. Open the file again, Delete 2 words in the last line and quit without saving
```
vi samplefile.txt
shift+g
esc
dw
:q!
```
## 3. Merge the cust1.txt and cust2.txt in the name of custmerged.txt with cust2.txt contents first and cust1.txt content next
```
cust2.txt > custmerged.txt
cust1.txt >> custmerged.txt
```
## 4. Count the number of lines in custmerged.txt and add the count in the last line of the custmerged.txt using command without using vi editor
```
wc -l custmerged.txt >> custmerged.txt
```
## 5. Add a header as custno,firstname,lastname,age,profession in the first line of the custmerged.txt using command without using vi editor
#(Hint: Think of using tempfiles, first create a temp file with header, then add data, then move tempfile to final filename)
```
vi tempfile1.csv

provide headers - custno,firstname,lastname,age,profession with data into the tempfile1.csv

mv tempfile1.csv custmerged.txt
```

## 6. Find for the number of occurances of the word Pilot
```
grep Pilot custmerged.txt
```

## 7. Find for Pilot and replace with Aircraft Pilot in the custmerged.txt (use the commmand sed -i 's/Pilot/AircraftPilot/g' custmerged.txt)
```
sed 's/Pilot/AircraftPilot/' custmerged.txt
```

## 8. Count the number of words and lines in the custmerged.txt
```
wc -l custmerged.txt

wc -w custmerged.txt
```

## 9. List and display only the last file created. List and display only the last but one file created in the current folder.
```
ls -lrt | tail -n 1

cd dir1
[hduser@localhost dir1]$ ls -lrt | tail -n 1
```
## 10. Copy the custmerged.txt in the name of custmeredcopied.txt retaining the timestamp of the original file in the copied file.
```
cp -p custmerged.txt custmergedcopied.txt
```
## 11. Goto /tmp directory, staying in /tmp , create directories inside /home/hduser path as src/custdata using placeholder ~ , then goto ##/home/hduser/src/custdata,then goto /home path using absolute path method, come back to /home/hduser/src/custdata using the respective placeholder, go to 2 ## levels higher using the respective placeholder
```
cd temp
ls /home/hduser
mkdir -p ~/src/custdata
cd /home/hduser/src/custdata
cd /home
cd ~/src/custdata
cd ~
cd /
```
## 12. Copy the custmerged.txt inside the /home/hduser/src/custdata and rename the directory custdata as customerdata
```
cp custmerged.txt ~/src/custdata/
cd src
mv custdata customerdata
```
## 13. Move & rename the /home/hduser/src/customerdata into the directory /tmp/custdata/process
```
mkdir -p /tmp/custdata/process
mv  /home/hduser/src/customerdata /tmp/custdata/process
```
## 14. Create a zerobyte file namely success inside /tmp/custdata/process
```
touch /tmp/custdata/process/success
```
## 15. Create a dir called /tmp/custdata/archive
```
mkdir /tmp/custdata/archive
```
## 16. compress using gzip compression the /tmp/custdata/process/custmerged.txt file and move into /tmp/custdata/archive
```
gzip /tmp/custdata/process/custmerged.txt
mv /tmp/custdata/process/custmerged.txt.gz /tmp/custdata/archive
```
## 16.B Remove the /tmp/custdata/process directory.
```
rm -rf /tmp/custdata/process
```
## 17. Create a user in your name, set password as hduser, switch user to the user created, create a file inside /tmp directory in your name logged in your name.
```
sudo useradd SamDany
sudo passwd SamDany
> /tmp/SamDany.txt
```
## 18. Remove write access for user using octal number and naming methods using chmod, try writing the file using vi editor
```
chmod 077 /tmp/SamDany.txt
vi /tmp/SamDany.txt
```
## 19. Repeate the step 18 for other user also, you can use hduser as others here.
```
chmod 070 /tmp/SamDany.txt
vi /tmp/SamDany.txt
```
## 20. Create a local variable called welcomemessage="Welcome aspirants", convert it into environmental variable, check whether it is added in the env variable.
```
welcomemessage="Welcome aspirants"
echo $welcomemessage
export welcomemessage
echo welcomemessage
```
## 21. Add the env variable into .bashrc profile and ensure the env variable is set every time.
```
sudo nano .bashrc
scroll down to the end of the file
add the below varaible
export welcomemessage="Welcome aspirants"

open a new terminal and 
printenv | grep welcomemessage


```




    





