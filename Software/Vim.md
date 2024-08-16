Status: **Editing**

Tags: [[Software]]

# Vim

![[../z_images/vi-vim-cheat-sheet.gif]]

- **Open a file**: `vim filename`
- **Open Vim without a file**: `vim`
- **Normal Mode**: The default mode for navigation and manipulation.
- **Insert Mode**: For inserting text.
- **Visual Mode**: For selecting text.
- **Command-Line Mode**: For executing commands.
#### Navigate
- **hjkl** Move
- **w** Move to the start of the next word
- **b** Move to the start of the previous word
- **0** Move to the beginning of the line
- **$** Move to the end of the line
- **gg** Move to the beginning of the file
- **G** Move to the end of the file
- **Ctrl-u** Scroll up half a screen
- **Ctrl-d** Scroll down half a screen
- **/pattern** Search for 'pattern' in the file.
- **n** Move to the next search result.
- **N** Move to the previous search result.
- : jump to specific line
#### Edit
- **i** Enter Insert mode before the cursor
- **I** Enter Insert mode at the beginning of the line
- **a** Enter Insert mode after the cursor
- **A** Enter Insert mode at the end of the line
- **o** Open a new line below and enter Insert mode
- **O** Open a new line above and enter Insert mode
- **x** Delete the character under the cursor
- **dd** Delete the current line
- **yy** Yank (copy) the current line
- **p** Paste after the cursor
- **u** Undo the last change
- **Ctrl-r** Redo the last undone change
#### Visual
- **v** Enter Visual mode
- **V** Enter Visual Line mode
- **Ctrl-v** Enter Visual Block mode
- **d** Delete the selected text
- **y** Yank (copy) the selected text
- **p** Paste the yanked text after the cursor.
- **P** Paste the yanked text before the cursor.
- **>** Indent the selected text
- **<** Unindent the selected text
#### Buffers
- **List Buffers**: `:ls`
- **Switch Buffer**: `:b buffer_number` or `:b buffer_name`
- **New Buffer**: `:edit filename`
- **Add Buffer(without closing current)**: `:badd filename`
- **Delete Buffer**: `:bd`
- **Hide Buffer**: `:hide`
- **Rename Buffer**: `:file new_name`

#### Registers
- **Show registers** `:reg r`
- **Access reg** `"r`
- **Paste reg** `"rp`
	- insert mode you can use CTRL-r
- "0 latest yank
- "1 to "9 latest delete
- **Read-only registers:**
    
    - **".**: Stores the last inserted text.
    - **"%**: Contains the current file path. Use `:let @+=@%` to copy the file path to the clipboard.
    - **":**: Holds the most recently executed command. Re-execute with `@:`.
    - **"#**: Represents the name of the alternate file (last edited file). Switch files with `:e <Ctrl-r #>`.
- **Special registers:**
    
    - **Expression register ("=)**: Allows executing expressions and pasting results. Example: `Ctrl-r = 2+2` yields `4`.
    - **Search register**: Contains the last searched text. Example: Replace the last searched term with `:%s/<Ctrl-r />/new_term/g`.
- **Macros**:
    
    - Recorded actions are stored in registers. Use `qw` to record a macro into register "w".
    - Edit macros directly by modifying the register's contents. Example: `:let @w='<Ctrl-r w>'`.
    - Share macros by copying them to the clipboard and executing them with `@+`.
# References


#### Misc
**nu**: Show line numbers.
**on**: Enable syntax highlighting.
**%s/old/new/g** Replace all occurrences of 'old' with 'new' in the file.
**10,20s/old/new/g**
**.** Repeat the last command.
**~** toggle case
**r** replace the character with another
:split "filepath" :vsplit
:tabnew gt gT :tabn 1 :tabs :tabclose :tabonly
:filename change filename