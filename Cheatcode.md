# About Cron Jobs
Cron is a time-based job scheduler in Unix-like operating systems, including Linux. It allows you to automate repetitive tasks by scheduling them to run at specific intervals.

# Scheduling a Cron Job with `crontab`
1. Open a terminal window.
- To open your current cron jobs: `crontab -e`
2. To edit your user's crontab, type:
   This will open the default text editor (usually vi or nano) with your crontab file.
3. In the editor, add a new line for your cron job. Each line represents a single cron job entry.
4. The general syntax of a cron job entry is as follows:
   The five asterisks represent the time and date fields.
   - The first field represents minutes (0-59)
   - The second field represents hours (0-23)
   - The third field represents days of the month (1-31)
   - The fourth field represents months (1-12)
   - The fifth field represents days of the week (0-6, where 0 is Sunday and 6 is Saturday)
5. After adding the desired cron job(s), save the file and exit the text editor.

# Additional Commands
- To list your current cron jobs: `crontab -l`
- To remove your crontab: `crontab -r`
# Common Bash Shell Commands

## Informational Commands
- Display current date/time: `date`
- Show your username: `whoami`
- Display hostname: `hostname`
- Display running processes: `ps`
- Display system statistics: `top`

## File Commands
- List files/directories: `ls`
- Change current directory: `cd`
- Display current directory: `pwd`
- Create a new directory: `mkdir`
- Remove files/directories: `rm`
- Copy files/directories: `cp`
- Move or rename files: `mv`
- Create an empty file: `touch`
- Change file permissions: `chmod`
- Change file ownership: `chown`

## Content Commands
- Display file content: `cat`
- Display beginning of file: `head`
- Display end of file: `tail`
- View content with pagination: `less` / `more`
- Search patterns in files: `grep`
- Sort lines in text files: `sort`
- Display unique lines: `uniq`

## Navigational Commands
- Change current directory: `cd`
- List files/directories: `ls`
- Display current directory: `pwd`
- Navigate using stack: `pushd` / `popd`

## Compression Commands
- Create/extract archives: `tar`
- Compress/decompress using GZIP: `gzip` / `gunzip`
- Create/extract ZIP archives: `zip` / `unzip`
- Tar with gzip (.tar.gz): Combine archiving and compression

## Networking Commands
- Send ICMP echo requests: `ping`
- Display network interfaces: `ifconfig` / `ip`
- Download files from web: `wget` / `curl`

# Creating and Running the `count_lines.sh` Script

1. **Create a New File**
   - Create a new file called `name.sh`.

2. **Open a Text Editor** vim or nana here
   - Open a text editor of your choice.
   - Create a new file named `name.sh`.

3. **Add Shebang and Script Content**
   - Start the script with a shebang line (`#!/bin/bash`) to specify the shell interpreter.Bash here
   - Add the script content.
     ```bash
     #!/bin/bash
     
4. **Make the Script Executable**
   
   - Run: `chmod +x name.sh`

5. **Run the Script**
   
     - ./name.sh 
     
# Linux Commands

## Develop shell scripts using Linux commands, environment variables, pipes, and filters.

| Description                                                                                                                                                       |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| - The `wc -l` command is used to count lines.                                                                                                                     |


## Environment Variables

| Description                                                                                                                                                       |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| - The `$#` variable holds the number of script arguments.                                                                                                         |
| - The `$1` refers to the first argument passed to the script.                                                                                                     |

## Pipes and Filters

| Description                                                                                                                                                       |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| - The script demonstrates the use of pipes and filters by combining `find` and `wc -l` to count lines in files.                                                   |
| - The `<` operator is used to direct the contents of a file to `wc` for line counting.                                                                            |
| - Pipes (`|`) are not explicitly used in this script, but they are commonly used to send the output of                                                            |
| - one command as input to another, enabling powerful data processing.                                                                                             |



