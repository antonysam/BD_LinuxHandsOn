## 1) Goto /home/hduser directory and Create 2 files namely cust1.txt and cust2.txt with the first 10 lines copied from /home/hduser/hive/data/custs and last 10 lines copied from /home/hduser/hive/data/custs.
```
1) cd /home/hduser or ~
2) > /hive/data/custs
      provide some data in the cust.txt
3) head -10 cust.txt | tail -10 cust.txt > cust1.txt
4) head -10 cust.txt | tail -10 cust.txt > cust2.txt
```
