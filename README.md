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

  - ### Quitting Without Saving Edits
 
      What if you want to wipe out all of the edits you have made in a session and then return to the original file? The command:
            
                        $ :e!

      returns you to the last saved version of the file, so you can start over.
 
      Suppose, however, that you want to wipe out yours edits and then just quit **vi?** The command:
            
                        $ :q!

- ### vi Commands

    **vi** has two modes: command mode and insert mode. As soon as you enter a file, you are in command mode, and the editor is waiting for you to enter a command. Commands enable you to move anywhere in the file, to perform edits, or to enter insert mode to add new text. Commands can also be given to exit the file (saving or ignoring your edits) in order to return to the Unix prompt.

    You can think of the different modes as representing two different keyboards. In insert mode, your keyboard functions like a typewriter. In command mode, each key has a new meaning or initiates some instruction.

    When you open a new file, **vi** starts in *command mode* and interprets the first keystroke (i) as the insert command. All keystrokes made after the nsert command are considered text until you press **ESC**. If you need to correct a mistake while in insert mode, back-space and type over the error.
  
  - ### Opening a File
 
      **vi** is the Unix command that invokes the vi editor for an existing file or for a brand new file. The syntax for the **vi** command is:
