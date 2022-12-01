# Linux- Self Study

## :black_circle: Yellow Dog Updater, Modified (YUM)

**YUM** is the primary package management tool for installing, updating, removing, and managing software packages in Red Hat Enterprise Linux. YUM performs dependency resolution when installing, updating, and removing software packages. YUM can manage packages from installed repositories in the system or from .rpm packages. The main configuration file for YUM is at /etc/yum.conf, and all the repos are at /etc/yum.repos.d.

#### It's easy to manage packages in Linux with YUM. At the command line, enter:

> yum -option command

#### There are many options and commands available to use with YUM. I've listed some commonly-used commands for YUM below:

| Command | Purpose |
| ----------- | ----------- |
| yum install | Installs the specified packages |
| remove | Removes the specified packages |
| search | Searches package metadata for keywords |
| info | Lists description |
| update | Updates each package to the latest version |
| repolist | Lists repositories |
| history | Displays what has happened in past transactions |

#### The following are commonly-used options with YUM:

 Options | Purpose |
| ----------- | ----------- |
| -C | Runs from system cache |
| --security | Includes packages that provide a fix for a security issue |
| -y	 | Answers yes to all questions |
| --skip-broken	 | Skips packages causing problems |
| -v | Verbose |

> The history option gives you an overview of what happened in past transactions. This provides some useful information, like the date when the transaction happened and what command was run.


> ![alt text](https://www.redhat.com/sysadmin/sites/default/files/styles/embed_large/public/2020-04/Picture1.png?itok=MDH-JPPX)

##### You can undo or redo certain transactions using the history command. Here is an example of undoing a transaction:
  > yum history undo <id>
  
##### YUM provides many options for package management. For detailed option information, look at:
  > man yum 
  
  > yum –help.
  
# :black_circle: What is Soft Link And Hard Link In Linux?
  
A link in UNIX is a pointer to a file. Like pointers in any programming languages, links in UNIX are pointers pointing to a file or a directory. Creating links is a kind of shortcuts to access a file. Links allow more than one file name to refer to the same file, elsewhere. 

There are two types of links :

:small_orange_diamond: Soft Link or Symbolic links
  
:small_orange_diamond: Hard Links

  ### :point_right: A soft Link:

 - A soft link is similar to the file shortcut feature which is used in Windows Operating systems.
    Each soft linked file contains a separate **Inode** value that points to the original file.
    As similar to hard links, any changes to the data in either file is reflected in the other. 
    Soft links can be linked across different file systems, although if the original file is deleted or moved, the soft linked file will not work         correctly (called hanging link).
- ls -l command shows all links with first column value l? and the link points to original file.
- Soft Link contains the path for original file and not the contents.
- Removing soft link doesn’t affect anything but removing original file, the link becomes “dangling” link which points to nonexistent file.
- A soft link can link to a directory.
- The size of the soft link is equal to the length of the path of the original file we gave.
  E.g if we link a file like ln -s /tmp/hello.txt /tmp/link.txt then the size of the file will be 14bytes which is equal to the length of the   “/tmp/hello.txt”.
- If we change the name of the original file then all the soft links for that file become dangling i.e. they are worthless now.
- Link across file systems: If you want to link files across the file systems, you can only use symlinks/soft links.
- Command to create a Soft link is: 

  >  ln  -s [original filename] [link name] 
  
### :point_right: A hard Link:
  
- Each hard linked file is assigned the same **Inode** value as the original, therefore they reference the same physical file location. Hard links more flexible and remain linked even if the original or linked files are moved throughout the file system, although hard links are unable to cross different file systems.
- ls -l command shows all the links with the link column shows number of links.
- Links have actual file contents
- Removing any link, just reduces the link count, but doesn’t affect other links.
- Even if we change the filename of the original file then also the hard links properly work.
- We cannot create a hard link for a directory to avoid recursive loops.
- If original file is removed then the link will still show the content of the file.
- The size of any of the hard link file is same as the original file and if we change the content in any of the hard links then size of all hard link - - - files are updated.
- The disadvantage of hard links is that it cannot be created for files on different file systems and it cannot be created for special files or directories.
- Command to create a hard link is: 
 

  >  ln  [original filename] [link name] 

