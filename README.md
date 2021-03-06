## Shellcode Generator
![alt text](https://github.com/ngimb64/Shellcode-Generator/blob/main/ShellcodeGen.png?raw=true)

## Prereqs
This program was designed for Python3 on Linux systems with objdump utility.
The modules used should already be included in the Python3 default installation.

## Purpose
The purpose is to run objdump on selected file, grab bytes, & format as shellcode.
Ideally this program can be added to environment executables/path as a handy terminal utility.

## Installation
- Run the setup.py script to build a virtual environment and install all external packages in the created venv.

> Example:<br>
> python3 setup.py "venv name"

- Once virtual env is built traverse to the (Scripts-Windows or bin-Linux) directory in the environment folder just created.
- In the bin directory, run the command `source activate` to activate the virtual environment.

## How it works
> Example:<br>
> python3 shellcodeGen.py &lt;executable\_name&gt;

- If arg is not passed, the user is prompted for input
- Selected executable is run in objdump, the output in intel syntax is redirected to a temporary text file
- The text file is then iterated over line by line; grabbing bytes, stripping whitespace, & formatting it as shellcode
- The shellcode formatted for the current line will be appended to a variable
- Once all iterations are complete the temp file is deleted and final shellcode result is provided
