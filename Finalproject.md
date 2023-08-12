# Project Scenario: Automatic Backup Script for Encrypted Password Files

# Company
ABC International Inc.

#Problem
Manual backup of encrypted password files introduces human error, lowers security, and is time-consuming.

## Task
Create a script to automatically back up updated encrypted password files within the last 24 hours.

## Objective
Demonstrate advanced shell scripting skills by solving a real-world automation problem.

# Learning Goals
1. Develop practical shell scripting expertise.
2. Enhance file manipulation and automation skills.
3. Apply security best practices in file handling.
4. Gain experience in scheduling and task automation on Linux.
5. Improve ability to write clear and maintainable scripts.
6. Learn to provide code reviews and evaluate peers' technical work.

# code
#!/bin/bash

 #This checks if the number of arguments is correct
 #If the number of arguments is incorrect ( $# != 2) print error message and exit
if [[ $# != 2 ]]
then
  echo "backup.sh target_directory_name destination_directory_name"
  exit
fi

# This checks if argument 1 and argument 2 are valid directory paths
if [[ ! -d $1 ]] || [[ ! -d $2 ]]
then
  echo "Invalid directory path provided"
  exit
fi
 echo "Welcome to Maham's project"
 
# [TASK 1]
#Setting of two variable represent target and des.directory
targetDirectory=$1 
destinationDirectory=$2

# [TASK 2]
#printing of Target and Destination directory
echo "Target director is: $targetDirectory"
echo "Destination directory is: $targetDirectory"

# [TASK 3]
#Timestamp in seconds
currentTS=$(date +%s)


# [TASK 4]
#Backing up the file storing and compress by tar and gw:algo of compress
backupFileName="backup-$currentTS.tar.gz"
#echo "Backup file name: $backupFileName"
# We're going to:
   1: Go into the target directory
   2: Create the backup file
   3: Move the backup file to the destination directory

# To make things easier, we will define some useful variables...

# [TASK 5]
#path of current directory-currently working
origAbsPath=$(pwd) #'pwd'
echo "Origin Path:$origAbsPath"
# [TASK 6]
cd  "$destinationDirectory" || exit
destAbsPath=$(pwd) 

# [TASK 7]
cd "$origAbsPath"    || exit   # <- changed original directory

cd "$targetDirectory"  || exit  # <- change to target directory
targetDirAbsPath=$(pwd)
echo "Target Directory Absolute Path: $targetDirAbsPath" 
# [TASK 8]
yesterdayTS=$((currentTS -24 * 60 * 60)) #YesterdayTS->24 hours (-) for yesterdayTS

declare -a toBackup
#array to declare backup

for file in $(ls) # [TASK 9]      #return all file or directory

do

  # [TASK 10]
  if [[ $(date -r "$file" +%s) -gt $yesterdayTS ]];#-gt greaterthan -r yesterdayhumanreadable
  then
  echo "Modify file last 24 hours: $file"
    # [TASK 11]
    toBackup+=($file)
    
  fi
done



# [TASK 12]
# Create .tar archive
tar -cvf "$backupFileName" ${toBackup[@]}



# [TASK 13]
# Move the backup file to the destination directory
mv "$backupFileName" "$destAbsPath"



# Congratulations! You completed the final project for this course!

