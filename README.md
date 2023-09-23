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

  - ### Saving and Quitting a File

      You can quit working on a file at any time, save your edits, and return to the Unix prompt. The **vi** command to quit and save edits is **ZZ**. Note that **ZZ** is capitalized.

      Let us assume that you do create a file called *practice* to practice vi commands, and that you type in six lines of text. To save the file, first check that you are in command mode by pressing *ESC*, and then **ZZ**.

      You can also save your edits with ex commands. Type **:w** to save (write) your file but not quit **vi**; type **:q** to quit if you have not made any edits; and type **:wq** to both save your edits and quit. (**:wq** is equivalent to **ZZ**.)

  - ### Quitting Without Saving Edits
 
      What if you want to wipe out all of the edits you have made in a session and then return to the original file? The command:
            
                        $ :e!

      returns you to the last saved version of the file, so you can start over.
 
      Suppose, however, that you want to wipe out yours edits and then just quit **vi?** The command:
            
                        $ :q!

- ### Simple Editing
    
    - ### vi Commands
    
        **vi** has two modes: command mode and insert mode. As soon as you enter a file, you are in command mode, and the editor is waiting for you to enter a command. Commands enable you to move anywhere in the file, to perform edits, or to enter insert mode to add new text. Commands can also be given to exit the file (saving or ignoring your edits) in order to return to the Unix prompt.
    
        You can think of the different modes as representing two different keyboards. In insert mode, your keyboard functions like a typewriter. In command mode, each key has a new meaning or initiates some instruction.
    
      There are several ways to tell **vi** that you want to begin insert mode. One of the most common is to press **i**. The **i** does not appear on the screen, but after you press it, whatever you type will appear on the screen and will be entered into the buffer. The cursor marks the current insertion point. To tell **vi** that you want to stop inserting text, press *ESC*. Pressing *ESC* moves the cursor back one space (so that it is on the last character you typed) and returns **vi** to command mode.
    
        When you open a new file, **vi** starts in *command mode* and interprets the first keystroke (i) as the insert command. All keystrokes made after the nsert command are considered text until you press **ESC**. If you need to correct a mistake while in insert mode, back-space and type over the error.

    - ### Moving the Cursor

        You may spend only a small amount of time in an editing session adding new text in insert mode; much of the time you will be making edits to existing text.

        In command mode you can position the cursor anywhere in the file. Since you begin all basic edits (changing, deleting, and copying text) by placing the cursor at the text that you want to change, you want to be able to move the cursor to that place as quickly as possible.
 
        There are **vi** commands to move the cursor:

        - Up, down, left or right—one *character* at a time
        - Forward or backward by blocks of *text* such as wwords, sentences, or paragraphs
        - Forward or backward through a file, one screen at a time

    - ### Single Movements

        The keys **h**, **j**, **k**, and **l**, right under your fingertips, will move the cursor:
        - h = Left, one space
        - j = Down, one line
        - k = Up, one line
        - l = Right, one space

    - ### Numeric Arguments
     
        You can precede movement commands with numbers. The command `4l` allow us move the cursor four spaces to the right, just as if you had typed `l`four times (`llll`).

    - ### Movement within a line
     
        - 0 (digit zero) = Move to beginning of file
        - $ = Move to end of file


    - ### Movement by Text Blocks
    
        - [ ] You can also moove the cursor by blocks of text: words, sentences, paragraphs, etc. The `w` command moves the cursor forward one word at a time, counting symbols and punctuation as equivalent to words.
        - [ ] You can also move by word, not counting symbols and punctuation, using the W command. (You can thinkg of this as a "capital" Word.)
        - [ ] To move backward by word, use the **b** command. Capital B allows you to move backward by word, not counting punctuation.
        - [ ] Movement commands take numeric arguments; so, with either the **w** or **b** commands you can multiply the movoement with numbers. **2w** moves forward two words; **5B** moves back five words, not counting punctuation
        - [ ] To move to a specific line, you can use the **G** command. Plain **G** goes to the end of the file, **1G** goes to the top of the file, and **42G** goes to line 42.

    - ### Simple Edits
     
        Once you enter text, you have to be able to change it, delete it, move it or copy it.

        In **vi** you can perfom any of these edits with a few basic keystrokes:

        - [ ] **i** for insert
        - [ ] **a** for append
        - [ ] **c** for change
        - [ ] **d** for delete

        ✨ To move or copy text, you use pairs of commands. You move text with a **d** for "delete", then a **p** for "put".
      
        ✨ You copy text with a **y** for "yank", then a **p** for "put".

    - ### Appending Text

        You can append text at any place in your file with the append command, a. This works in almost the same way as i, except that text is inserted **after** the cursor rather than **before** the cursor. You may have oticed that when you press i to enter insert mode, the cursor does not move until after you enter some text. By contrast, when you press **a** to enter insert mode, the cursor moves one space to the right. When you enter text, it appears after the original cursor position.

    - ### Changing Text

        You can replace any text in your file with the change command, c.

        To tell c how much text to change, you combine c with a **movement command** (See movements command above). In this way, a movement command serves as a `text object` for the c command to affect. For example, c can be used to change text from the cursor:

        - [ ] **cw** To the end of a word
        - [ ] **c2b** Back two words
        - [ ] **c$** To the end of line
        - [ ] **c0** To the beginning of line

        After issuing a change command, you can replace the identified text with any amount of new text, with no characters at all, with one word, or with hundreds of lines. c, like i and a, leaves you in insert mode until you press the ESC key.

      When the change affects only the current line, vi marks the end of the text what will be changed with a $ sign, so that you can see what part of the line is affected. (See the example for cw, next.)

      **Words**

      To change a word, combine the c (change) command with w for word. You can replace a word (cw) with a longer or shorter word (or any amount of text). cw can be thought of as "delete the word marked and insert new text until ESC is pressed."

      cw also works on a portion of a word. For example, to change *spelling* to *spelled*, you can position the cursor on the *i* letter, type cw, then type ed, and finish with ESC.
