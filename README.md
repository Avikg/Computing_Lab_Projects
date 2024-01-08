# OS Programming

Part - A (System Calls - 1)
In this part, you will write a basic shell. A parent process will give a prompt shell> to the
user and wait for a command (from a set of commands given below) to be typed. For each
command, the parent process will fork a child process which will execute that command.
Normally, the parent process will wait for the command to be finished, after which it will
give the shell> prompt again and wait for the next command.
However, if the command is followed by an & (ampersand) character (with or without
blanks after the command), the parent process will return immediately (that is, it will not
wait for the child to finish the command), and wait for the next command.
Implement the following commands:-
1. pwd - shows the present working directory
2. cd <directory_name> - changes the present working directory to the directory
specified in <directory_name>. A full path to a directory may be given.
3. mkdir <directory_name> - creates a new directory specified by <dir>.
4. ls <flag> - shows the contents of a directory based on some optional flags, like
ls -al, ls, etc. See man page of ls to know more about the flags.
5. exit - exits the shell
6. help - prints this list of commnds
7. If you type any other command at the prompt, the shell should just assume it is
an executable file and try to directly execute it.
Note:- A proper error message should be shown at the terminal/prompt, if the above
manual (given to user) is not followed.


Part - B (System Calls - 2)
You need to extend the shell created in the previous part-A using I/O redirection to make it
possible to:-
1. pipe one command through the other using the ‘|’ operator. For example, it should be
possible to give the following commands to your program:
ls –al | more or cat text.txt | grep abcd


Part - C (readline library)
Extend the shell created in the previous part-B to incorporate some shell functionalities
1. Multi-Line commands:- A single command may be extended to a multiline
command using backslash(\) character. Example shown in Fig. 1
Fig. 1:- Example of Multi-Line Command
2. Command history:- Using the up arrow we can execute the previous commands.
3. Command Editing:- If a long command has some mistake, the user may press
Ctrl+A to move the cursor to the start of the line and make corrections.
Part - D (ncurses library)
Extend the shell created in the previous part-C using ncurses by introducing your own ‘vi’
command which is a text editor. vi <filename> will open an editor terminal, that
supports the following functionalities after taking input from your keyboard:-
1. Toggle keys - up, down, left, right arrow keys to toggle the cursor between lines
2. Escape Key - ESC to close the editor terminal
3. Delete Key - DELETE - to delete the current character pointed out by the cursor.
4. Insert character keys - [a-z], [A-Z], [0-9], characters at the location pointed out by
the cursor.
5. Ctrl + S - save as a file
6. Ctrl + X - exit the editor terminal
7. After a successful exit operation, mention the number of lines, number of words and
number of characters written/modified in the initial shell prompt.

Part - E (Threads)
You need to extend the shell created in the previous parts by using threading concept to
calculate vector operations. You need to use pthreads library for creating threads and
distributing jobs. Using the pthread library in your shell implement the following
commands:-
1. addvec <file_1> <file_2> -<no_thread>:- Addition of two vectors,
<file_1> and <file_2> both contain a line with n space separated numbers denoting a
n-dimensional vector v, (v ∈ R
n
). <no_thread> denotes the number of threads to
run. The default (if not anything mentioned is 3)
2. subvec <file_1> <file_2> -<no_thread>:- Subtraction of two vectors, v1
- v2, v1∈ <file_1> and v2 ∈ <file_2> both contain a line with n space
separated numbers denoting a n-dimensional vector v, (v ∈ R
n). <no_thread>
denotes the number of threads to run. The default (if not anything mentioned is 3).
3. dotprod <file_1> <file_2> -<no_thread>:- vector dot product of two
vectors, <file_1> and <file_2> both contain a line with n space separated numbers
denoting a n-dimensional vector v, (v ∈ R
n). <no_thread> denotes the number
of threads to run. The default (if not anything mentioned is 3).
