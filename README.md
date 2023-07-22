- ### The vi Text Editor

- ### Opening and Closing Files

    You can use vi to edit any text file. vi copies the file to be edited into a *buffer* (an area temporarily set aside in memory), displays the buffer (though you can see only one screenful at a time), and lets you add, delete, and change text. When you save your edits, vi copies the edited buffer back into a permanent file, replacing the old file of the same name. Remember that you are always working on a copy of your file in hte buffer, and that your edits will not affect your original file until you save the buffer. Saving your edits is also called "writing the buffer", or more commonly, "writing your file".

  - ### Opening a File
 
      **vi** is the Unix command that invokes the vi editor for an existing file or for a brand new file. The syntax for the **vi** command is:
            
                        $ vi [filename]

    The brackets shown on the above command line inicate that the filename is optional. The brackets should not be typed. The *$* is the Unix prompt. If the filename is omitted, vi will open an unnamed buffer. You can assign the name when you write the buffer into a file. For right now, though, let us stick to naming the file on the command line.
    
    When you want to open a new file in a directory, give a new filename with the **vi** command. For example, if you want to open a new file called **practice** in the current directory, you would enter:

                        $ vi practice

    Since this is a new file, the buffer is empty and the screen appears as follows:

                        ~ vi practice
                        ~
                        ~
                        "practice" [New file] 
    
    The tildes (~) down the lefthand column of the screen indicate that there is no text in the file, not even blank lines. The prompt line (also called the status line) at the bottom of the screen echoes the name and status of the file.

    You can also edit any existing text file in a directory by specifying its filename. Suppose that there is a Unix file with the pathname */home/john/letter*. If you already in the */home/john* directory, use the relative pathname. For example:

                        $ vi letter

    brings a copy of th efile letter to the screen.

    If you are in another directory, give the full pathname to begin editing:


                        $ vi /home/john/letter

  - ### Opening a File
 
      **vi** is the Unix command that invokes the vi editor for an existing file or for a brand new file. The syntax for the **vi** command is:
            
                        $ vi [filename]
