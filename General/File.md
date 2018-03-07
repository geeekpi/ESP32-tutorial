# File

## Load Files

Using `ampy` you can take Python code written on your computer and run it on a connected MicroPython board.  This gives you a simple workflow for exploring MicroPython.  Write code on your computer in your favorite text editor, then use ampy's run command to run it on a board!

To use the run command just specify a path to a Python file on your computer.  Ampy will send the file to the board, wait for it to finish running, and print any output from the program.

### Install ampy

Once Python is avaialble on your system you can easily install ampy from the Python package index.  If you're using Python 2.7.x open a terminal and run this command:

```
pip install adafruit-ampy
```

Note on some Linux and Mac OSX systems you might need to install as root with sudo:

```
sudo pip3 install adafruit-ampy
```

Or if you'd like to use Python 3.x run the pip3 command instead (using sudo if necessary):

```
pip3 install adafruit-ampy
```

## Run Code

For example create a file test.py on your computer and save inside it the following Python code:

```python
print('Hello world! I can count to 10:')
for i in range(1,11):
    print(i)
```

```
ampy --port /serial/port run test.py
```

Where /serial/port is the path or name of the serial port connected to the MicroPython board.

## File Operations

In addition to running code ampy you can also manipulate files on a MicroPython board's filesystem.

### Copy Files to Board

Use put command to copy a file to the board root directory.

```
ampy --port /serial/port put test.py
```

Or put it to a certain directory.

```
ampy --port /serial/port put test.py /foo/bar.py
```

### Copy Directories to Board

Put command can also copy a whole directory to the borad.

```
ampy --port /serial/port put A_Directory
```

### Read Files From Board

Use get command to read file from the borad.

```
ampy --port /serial/port get boot.py
```

With a target file you can get the file to your computer.

```
ampy --port /serial/port get boot.py board_boot.py
```

### Create Directories

Use mkdir command to create directories on the board in the root directory.

```
ampy --port /serial/port mkdir foo
```

Or a sub directory with a target.

```
ampy --port /serial/port mkdir /foo/bar
```

### List Directories

Use ls command to list directory on the board.

```
ampy --port /serial/port ls
```

Or list a sub directory.

```
ampy --port /serial/port ls /foo
```

### Remove Files & Directories

Use rm command to remove a file from the board.

```
ampy --port /serial/port rm test.py
```

Use rmdir command to remove a directory from the board.

```
ampy --port /serial/port rmdir /foo/bar
```
