### 1. Create a new Directory and sub directories
- This will create a parent directory 'SEE' in that directory will have [BEFA,CD,CN...] directories.
- ```mkdir -p SEE/{BEFA,CD,CN,AI,RSE}``` <br>
- This will create nested directories 
- ```mkdir -p SEE/CD/CompilerDesign/Notes``` <br>
- This will create a file in nested directories
- ```touch SEE/CD/CompilerDesign/Notes/CdNotes.txt```

### 2. Recursively copy all the directories and the sub-directories in an another directory
- ```cp -r SEE SEE_BACKUP```
- It'll copy all the content of SEE and paste it in SEE_BACKUP recursively.
- If SEE_BACKUP is not created it'll get created automatically in the process

### 3. Linux Permission Files represented as numbers
- r (read): 4 <br>
w (write): 2 <br>
x (execute): 1 <br>

- In the permission value 744, the first digit corresponds to the <b>user</b>, the second digit to the <b>group</b>, 
and the third digit to <b>others</b>. By adding up the value of each user classification, you can find the 
file permissions.

- For example, a file might have read, write, and execute permissions for its owner, and only read 
permission for all other users. That looks like this: <br>
Owner: rwx = 4+2+1 = 7 <br>
Group: r-- = 4+0+0 = 4 <br>
Others: r-- = 4+0+0 = 4 <br>
```chmod 700 file.txt```

### 4. How do you modify Linux file permissions?
- ```chmod ug+rwx example.txt``` <br>
- ```chmod o+r example2.txt``` <br>
- This grants read, write, and execute for the user and group, and only read for others. In symbolic mode, 
<b>chmod u</b> represents permissions for the user owner, <b>chmod g</b> represents other users in the file's group, 
<b>chmod o</b> represents other users not in the file's group. For all users, use <b>chmod a</b>.

- Maybe you want to change the user owner itself. You can do that with the <b>chown</b> command. Similarly, the 
<b>chgrp</b> command can be used to change the group ownership of a file.

### 5. To change the ownership of a file?
-  ```sudo chown user:group file.txt``` <br>
 In the place of user -> write the username and in the place of group write the group name
-  ```sudo chown sam:sam sample.txt```  or  ```sudo chown sam: sample.txt``` // changes both the user and group to sam <br>
-  ```sudo chown sam sample.txt``` // just changes the user ownership <br>
-  ```sudo chown :sam sample.txt``` // just changes the group ownership <br>

### 6. To search for a particular file in the particular directory 
-  ```find . -name "*.txt"``` // find all the files in the current directory ending with '.txt' <br>
-  ```find /home/ubuntu -name "*.txt"``` // find all the files in the given path '/home/ubuntu' ending with '.txt'

### 7. Search of a particular word in a file
- ```grep "error" sample.txt``` // It is will display where error is writtern in this file, 

### 8. Search for a word in all .txt of .log files 
- ```grep "This is a sample file" *.txt``` // same as below <br>
- ```grep "error" *.log``` // this will show where the word is located in the file 

