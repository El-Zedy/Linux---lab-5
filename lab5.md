# :heavy_check_mark: Lab 5

### :small_blue_diamond: 1. List the user commands and redirect the output to /tmp/commands.list:

	 ls /user/bin >> /tmp/commands.list
______________________________________________________________________________

### :small_blue_diamond: 2. Count the number of user commands:

	 ls /usr/bin/ | wc -l
______________________________________________________________________________

### :small_blue_diamond: 3. Get all the users names whose first character in their login is ‘g’:

	 grep "^g" /etc/passwd | cut -d ":" -f 1  

______________________________________________________________________________

### :small_blue_diamond: 4. Get the logins name and full names (comment) of logins starts with “g”:

	 grep "^g" /etc/passwd | cut -d ":" -f 1,5
______________________________________________________________________________

### :small_blue_diamond: 5. Save the output of the last command sorted by their full names in a file:

 	 grep "^g" /etc/passwd | cut -d ":" -f 1,5  | sort -t ":" -k 5 > ~/gNames
______________________________________________________________________________
	
### :small_blue_diamond: 6. Write two commands:

 ➡️	first: to search for all files on the system that named.bash_profile.
 	
 		 ls -R / | grep ".bash_profile"
 
 ➡️ Second: sorts the output of ls command on / recursively, 
    Saving their output and error in 2 different files and sending them to the background.

		 ls -R 2> ~/errFile 1> ~/outputFile &

______________________________________________________________________________

### :small_blue_diamond: 7. Display the number of users who is logged now to the system:

		 use w command
______________________________________________________________________________

### :small_blue_diamond: 8. Display lines 7 to line 10 of /etc/passwd file:

		 cat -n /etc/passwd | head -n 10 | tail -n 4
______________________________________________________________________________

### :small_blue_diamond: 9. Compress a file by compress, gzip, zip commands and decompress it again:

		∘ comperess filex
		∘ uncompress filex.z
		
		∘ gzip filex
		∘ gunzip filex.gz
		
		∘ zip filex.zip filex
		∘ unzip filex.zip
    
    
➡️ State the differences between compress and gzip commands.

	Compress will run faster and use less memory, but gzip will generally reach significantly higher levels of compression.
		
______________________________________________________________________________
		
### :small_blue_diamond: 10. What is the command used to view the content of a compressed file:

		 bzcat filex.bz2
______________________________________________________________________________

### :small_blue_diamond: 11. Backup /etc directory using tar utility:

		 tar cvf etc.tar /etc
______________________________________________________________________________

### :small_blue_diamond: 12. Starting from your home directory, find all files that were modified in the last two day:

		 ls -R /home 2> /dev/null | find /home -mtime -2 -ls
		 find ~ -mtime -2 -ls
______________________________________________________________________________
		
### :small_blue_diamond: 13. Starting from /etc, find files owned by root user:

	  ls -R /etc 2> /dev/null | find -perm 777
	  find /etc -user root
______________________________________________________________________________
		
### :small_blue_diamond: 14. Find all directories in your home directory:

		 find /home/username -type d
______________________________________________________________________________

### :small_blue_diamond: 15. Write a command to search for all files on the system that, its name is “.profile”: 

		 sudo find / -name ".profile" 2> /dev/null 
