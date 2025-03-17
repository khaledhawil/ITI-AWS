Linux Text Editors Tutorial
==========================

### Task 2: Running the Vim Tutorial

1. Open the terminal and start Vim tutorial:
```bash
vimtutor
```
   If `vimtutor` is not available, install Vim:
```bash
sudo yum install vim
```
2. Complete lessons 1-3 in `vimtutor`.
3. Exit `vimtutor` using `Esc` after that , type `:q!` and press `Enter`.

### Task 3: Editing a File in Vim

1. Open a new file in Vim:
```bash
vim helloworld
```
2. Enter insert mode by pressing `i` and add the following text:
```bash
Hello World!
This is my first file in Linux and I am editing it in Vim!
```
3. Press `ESC` to exit insert mode and save changes with `:wq`.
4. Reopen the file:
```bash
vim helloworld
```
5. Enter insert mode (`i`) and add:
```
I learned how to create a file, edit and save them too!
```
6. Exit without saving: `:q!`.
7. Reopen the file and observe that the last change was not saved.

#### Additional Vim Commands

* Delete a line: `dd`
* Undo last change: `u`
* Save without quitting: `:w`
* Cut a line: `yy`
* Paste a line: `p`
* Search for a word: `/word`

### Task 4: Editing a File in Nano

1. Open a new file in Nano:
```bash
nano cloudworld
```
2. Enter the following text:
```
We are using nano this time! We can simply start typing! No insert mode needed.
```
3. Save the file:
   * Press `CTRL+O` then `Enter` to confirm.
4. Press `CTRL+X` to exit.
5. Reopen the file to verify:
```bash
nano cloudworld
```
6. Exit Nano using `CTRL+X`.

### Task 5: Editing a File in Emacs

1. Open a new file in Emacs:
```bash
emacs spaceworld
```
2. Enter the following text:
```
We are using emacs this time! We can simply start typing! No insert mode needed.
```
3. Save the file:
   * Press `CTRL+X` then `CTRL+S` to confirm.
4. Press `CTRL+X` then `CTRL+C` to exit.
5. Reopen the file to verify:
```bash
emacs spaceworld
```
6. Exit Emacs using `CTRL+X` then `CTRL+C`.

### Summary

* `vimtutor` helps learn Vim basics.
* Vim requires switching between insert and command mode.
* `nano` is simpler, allowing direct text input.
* `emacs` is a powerful text editor with many features.

#### Key Commands

* Vim: `i`, `ESC`, `:wq`, `:q!`, `dd`, `u`, `yy`, `p`, `/`
* Nano: `CTRL+O`, `CTRL+X`
* Emacs: `CTRL+X`, `CTRL+S`, `CTRL+C`