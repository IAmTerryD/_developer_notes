# Command Line Prompts

cmd or cmd.exe: Opens the Windows Command Prompt.
cd: Changes the current directory.
dir: Lists the files and directories in the current directory.
cls: Clears the screen.
echo: Prints text to the console.
copy: Copies files.

move: Moves or renames files. 
```
move <folder> <directory> 

```
mkdir: Creates a new directory.
rmdir or rd: Removes a directory.
del or erase: Deletes files.
type: Displays the contents of a text file.
tasklist: Lists running processes.
taskkill: Terminates processes.
ping: Tests network connectivity.


# What is Virtual Environment (Python Development)

A virtual environment in Python is like having a separate, small, self-contained Python world on your computer. Imagine you have a room in your house where you can put all the stuff needed for a specific project, like books, tools, and materials. In this room, everything is organized just for that project, and it doesn't mix up with other things in your house.

Similarly, in Python programming, a virtual environment is a special room where you keep all the libraries and settings needed for a particular Python project. This way, you can have different projects with their own environments, and they won't interfere with each other. For example, one project can use an older version of a library, and another project can use a newer version, without any problems. It's like having multiple, separate rooms for different projects in your house.


## Install Virtual Environment


```
pip install virtualenv

```

# Create a Virtual Environment

Navigate to your Django project directory using the command prompt or terminal and create a virtual environment. You can name the virtual environment folder whatever you like; it's common to use names like "venv" or "env":

```
virtualenv env
```

This command creates a new directory called "venv" (or your chosen name) in your project directory, which contains a separate Python interpreter and a copy of the Python standard library.


# Activate the Virtual Environment:

To use the virtual environment, you need to activate it. The activation process varies depending on your operating system:

```
venv\Scripts\activate
```

# Install Djanog Inside Virtual Environment

The cmd line should now show (env), indicating we are in an isolated environment.

To install Django in this isolated environment: 

```
pip install django
```

# Move the environment inside Django Project

