# The Linux Command Line

## The Filesystem
### Commands
  - **pwd**: returns the current working directory
  - **ls**: lists all the files and directories in the current working directory
      - **-a**: returns hidden files and directories along with visible files and directories in the current working directory
      - **-l**: lists all contents of a directory in long format
      - **-t**: order files and directories by the time they were last modified
  - **cd**: switches to the directory you specify
  - **mkdir**: creates a new directory in the working directory
  - **touch**: creates a new file in the working directory
  
#### Excersises
  - **Change to the root of the filesystem**
    
        cd /
    
 - **Change to the home directory**
 
        cd ~
    
 - **Change to the parent directory**
      
        cd ..
     
 - **Change to the current directory**
      
        cd .
      
 ## File Permissions
[ - | d | l ] [rwx][rwx][rwx] [rwx][rwx][rwx]  [rwx][rwx][rwx]

 - The first part of the file permissions tells you if it's a file, directory or a symlink 
 - The second part of the file permissions is the permissions for the owner 
 - The third part of the file permissions is for the group 
 - The fourth part of the file permissions is for all other users
