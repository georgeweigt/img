
               Aztec C65 for the Apple // ProDOS
                        Version 3.2b
                   Additional Information, Ed 2
                        15 July 1986


 This document contains information about the 3.2b version of Aztec
C65, information that was added since the release document was
printed.

1.  Version numbers

 The signon message of some Aztec C65 programs say that they are 
version 3.2a. Don't worry, you have the correct software: even 
though individual programs are at version 3.2a, the product as a 
whole is at version 3.2b.


2.  End of Beta mode

 With this release, Aztec C65 is no longer in beta mode, so for
technical support, please call our technical support department at 201-
542-1795, or call our electronic bulletin board at 201-542-2793,
or send us a letter.

 No changes have been made in going from version 3.2a, which was the
last beta update, to version 3.2b. 


3.  Compiler bugs

 The 6502 compiler (named cc on native versions of Aztec C65, c65
on cross development versions) doesn't allow char-to-pointer casts. At
present, you can accomplish this by first casting the char to an int, then
casting the int to a pointer. For example,

    char c, *cp;
    cp = (char *)(int)c;


4.  Problems with the Apple // Parallel printer card

 When a parallel printer is opened on an Apple // that's in 40
column mode, the ROM on the Apple // parallel printer card writes an
inverse @ character to the screen.

 When screen echo is off and the parallel printer ROM writes a
character to the printer, the ROM resets the CH byte in memory, (ie,
location $24, the byte that defines the horizontal position of the screen
cursor); thus, if a program alternately writes to the printer and to the
screen, the characters that are written to the screen will overwrite one
another.


5.  convert bug

 It's been reported (but not verified by us here at Manx) that the
ProDOS convert program can't convert programs larger than 27K.


6.  Using the ROM graphics routines

 It's been reported (but not verified by us here at Manx) that some
of the ROM graphics routines (HPLOT, LINE) won't work when called
by an Aztec C-generated program.


7.  get_time() bug

 The get_time() function causes a program to crash. The problem is
that get_time calls the time function without passing it an argument
that's needed by time.


8.  Don't use the same names for variables and functions

 Using the same name for a variable and a function can lead to
hard-to-detect problems. For example, index is the name of a library
function that is pulled into most programs. If you use this as the name
of an uninitialized global variable, the linker will assign the variable the
same address as the function. And if you use this as the name of an
initialized global variable, the linker will assume that the index function
begins at the index variable and will not pull in the index function.

9.  System programs

 Many ProDOS system programs created using Aztec C65 will crash 
if they're started from the SHELL. There is no problem if they are 
started from the Basic Interpreter or automatically upon system start-up.

 The problem arises from the facts that
(1) the section of memory used by the SHELL's environment pages
(0xbc00-0xbf00) is still allocated when a system program is started,
and (2) a system program's pseudo stack grows down through the 
SHELL's environment pages. If the ProDOS MLI is told to perform an operation
and return information on the pseudo stack,
the MLI will not perform the operation if the information would be
placed in the SHELL's still-allocated environment pages.
