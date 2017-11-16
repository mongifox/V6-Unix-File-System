/**** Modified Version of V6 Unix File System

*********************************************************************************************************************************************

Author:
Manjesh Srinivasa (manjesh1060@gmail.com)

***********************************************************************************************************************************************

project statement :
To redesign unix file system v6 to remove limitation of 16Mb using the given guidlines.
it reads series of commands from user such as help, initfs, cpin, cpout, mkdir, q

**********************************************************************************************************************************************

file name: unixfilesystem.c

**Compiler Used:
GCC  Compiler

**Platform used:
UNIX and C

**Compiling and running code.

*Steps (On Ubuntu Linux PC):
1. Use file named unixfilesystem.c to compile and execute the main code.
2. The C file is compiled using command "gcc -o unixfilesystem unixfilesystem.c"
3. The same file can be run by typing command "./unixfilesystem" in terminal and respective output will be printed on same terminal.

*Steps (on cs1.utdallas.edu linux server):
1. The source code file was added to server using WINSCP software.
2. Next type "vi unixfilesystem.c" to see your Source code.
3. Type "i" to make any changes to the source code
4. Type ":wq" to save the changes made inside the code.
5. You can compile the source code by typing the command "gcc -o unixfilesystem unixfilesystem.c"
6. Use the command "./unixfilesystem" to run your source code.

**********************************************************************************************************************************************
** overall steps needed:

1. gcc -o unixfilesystem unixfilesystem.c
2. ./unixfilesystem

***********************************************************************************************************************************************
**Commands using in program output:

1.  initfs :: initialization of file system
        >>initfs <file system name> <number of blocks> <number of inodes>

2.  cpin :: creates new mv6 file and fill the contents of
 	>>cpin <external file> <mv6-file>

3.  cpout :: creates external file and copies content of mv6 file into external file
 	>>cpout <mv6-file> <external file>

4.  mkdir :: making directory in current directory
 	>>mkdir v6-dir

5.  q :: save all changes and quiet
	>>q

***********************************************************************************************************************************************
functions used:
1.  int fs_init(char* path, unsigned short parse_blocks,unsigned short total_inodes);
2.  void blk_read(unsigned short *target, unsigned short block_entry_num);
3.  void copy_into_inode(filesys_inode current_inode, unsigned int new_inode);
4.  void show_all_files();
5.  void blocks_chains(unsigned short parse_blocks);
6.  unsigned short allocateinode();
7.  void cpin(const char *pathname1 , const char *pathname2);
8. void out_plainfile(const char *pathname1 , const char *pathname2 , int blocks_allocated);
9. void out_largefile(const char *pathname1 , const char *pathname2 , int blocks_allocated);
10. void cpout(const char *pathname1 , const char *pathname2);
11. void largefile(const char *pathname1 , const char *pathname2 , int blocks_allocated);
12. void plainfile(const char *pathname1 , const char *pathname2 , int blocks_allocated);
13. void makedir(const char *pathname);
14. void update_rootdir(const char *pathname , unsigned short in_number);




***********************************************************************************************************************************************

Any problems or questions related to the code can be sent to manjesh1060@gmail.com
