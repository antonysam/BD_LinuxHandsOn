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





