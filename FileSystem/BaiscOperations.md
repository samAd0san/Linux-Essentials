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

### 3. To search for a particular file in the particular directory 
-  ```find . -name "*.txt"``` // find all the files in the current directory ending with '.txt' <br>
-  ```find /home/ubuntu -name "*.txt"``` // find all the files in the given path '/home/ubuntu' ending with '.txt'

### 4. Search of a particular word in a file
- ```grep "error" sample.txt``` // It is will display where error is writtern in this file, 

### 5. Search for a word in all .txt of .log files 
- ```grep "This is a sample file" *.txt``` // same as below <br>
- ```grep "error" *.log``` // this will show where the word is located in the file 

### 6. Rename the File
- ```mv oldname.txt newname.txt```<br>
- ```mv file1.txt file.txt```
- mv stands for "move". This command renames oldname.txt to newname.txt within the same directory. If you provide a different path, it will move the file to that location.

### 7. Moving the File
- ```mv file.txt /path/to/destination``` 
- ```mv /home/ubuntu/SEE/AI/ImpQns.txt /home/ubuntu/OtherFolder```
- This command moves file.txt from the current directory to /path/to/destination. If the destination is a directory, the file will be placed there with the same name. If the destination is a file name, file.txt will be renamed to that name and moved.

### 8. Delete the file or directory 
- ```rm file.txt```
- ```rm -r dir1``` // recursively
- The -r (or --recursive) option is used to delete a directory and all of its contents. This command removes dir1 and all files and subdirectories contained within it. Use this with care, as it will permanently delete all files and directories within dir1.

