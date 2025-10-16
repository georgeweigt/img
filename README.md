Instructions for use with Virtual ][

1. Start a virtual Apple 2e.

2. Click the Setup icon and put a SCSI card in Slot 7.

3. Add an OmniDisk to the SCSI card.

4. Click the Restart button.

5. Drag folder `KIX` or `AZTEC` to OmniDisk.

6. Click the Boot icon.

#

```
KIX Version 1.0 Command Summary

Controlling Directories
-----------------------

PWD           Print working directory
CD [dir]      Change directory
MKDIR dirlist Make directories
RMDIR dirlist Delete directories

Listing Directory/File Contents
-------------------------------

LS [path or dir] [;type] [redirect]
options:     
-L   List extended directory     
-F   List file types as:
     & txt  * bin  
     / dir  @ sys
-P   Print protection: (rwdn)            
     R  read   protect active             
     W  write  protect active             
     D  delete protect active             
     N  rename protect active            
     -  protection not active     
-N   Disable filename sort
;TYP List files of type:            
     SYS System   BIN Binary
     TXT Text     DIR Directory

ECHO pathname    Print each evaluation of pathname argument

LPR pathlist     Print files using the format set by CFG

CAT pathlist     Display or copy files   
options:     
-N     Number output lines
-B     Do not number empty lines     
-S     Remove adjacent empty lines     
-V     Print ctrl chars as ASCII

Manipulating Files,Dirs and Volumes
-----------------------------------

CP pathlist [path or dir]: Copy files to a file or directory
options:     
-I     Prompt to verify overwrite

MV pathlist [path or dir]: Move files to directory or rename file
options:     
-I     Prompt to rename each file
-F     Rename even if locked

RM pathlist       Remove files  
options:     
-I     Prompt to delete each file     
-F     Delete even if locked     
-R     Empty directory

CHMOD pathlist   Add/remove file access   
options:
+      Add access (permit option)     
-      Remove access (deny option)     
R      Read     
W      Write     
D      Deletion     
N      Rename

FORMAT (s,d) /volname  Format diskette

CPV (ss,dd) (s,d)      Copy volume

Comparing Files and Volumes
---------------------------

CMP file1 file2     Compare files

CMP (s,d) (s,d)     Compare volumes

SDIFF file1 file2   List text file differences

Searching Directories and Files
-------------------------------

FIND dirlist -filename  Find filename in and below directory level

GREP string pathlist    Look for string pattern in text files

System Date and Displays
------------------------

DATE [yymmddhhmm] [www]: Print or set the system date and time  
C40      Set 40 column mode
C80      Set 80 column mode
SD       Screen dump to printer
INTRO    An introduction to Kyan Pascal
MENU     Menu of system facilities
KIX      This help screen
QUIT     Exit the KIX shell

System Facilities
-----------------
PC       Pascal compiler/assembler
ED       Text editor
AS       6502 Assembler
```
```
Instructions for Kix text editor "ed".
"ed" starts in edit mode.
Press ESC to toggle between edit and command modes.

Cursor control in edit mode (^ is control key)

^S       Left arrow
^D       Right arrow

^E       Up arrow
^X       Down arrow

^A       Go back 1 word
^F       Go forward 1 word

^R       Go back 20 lines
^C       Go forward 20 lines

^T       Go to top of file
^V       Go to bottom of file

^Q       Delete to left of cursor
^G       Delete under cursor
^Y       Delete current line

^W       Find string backward
^Z       Find string forward

^O       Mark/cut block
^P       Paste block

Commands in command mode

S       Save file
Q       Exit without saving
X       Save file and exit
A       Set search string
B       Set replacement string
C       Set search/replace options
I       Include file
P       Set file name
G       Go to line
H       Help menu
```
