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
