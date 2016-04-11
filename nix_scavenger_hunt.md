# *nix Scavenger Hunt

Complete the following challenges using the command-line interface on your favorite
Unix or Linux operating system. You are welcome and encouraged to consult any
additional documentation online or in books.

Please add your answers/responses/text pastes to the document after each prompt.

Note: For some of the challenges you will need to reference files included with
this repository, so you will need to fork the repo into your own Github account
and then clone it to your development environment.

## The Challenges

### Navigating the Filesystem

* Get an idea of where you are in the operating system. Use the `pwd` command to find your "path to working directory"--your current location in the filesystem of your devbox. 

/home/cabox/workspace

* Discover more about this filesystem. Use `ls` (the "list" command)to see what is in this directory. *What directories and files do you see when you run `ls`?*

LICENSE    challenge_files        nix_scavenger_hunt_stretch.md                 
README.md  nix_scavenger_hunt.md

* You can use *options* to modify how a command runs. Try using `ls -alh` to see the contents of your current directory. *How are the results different when you use the `-alh` options?*

total 36K                                                                       
drwxrwxr-x  4 cabox cabox 4.0K Apr 10 21:06 .                                   
drwxr-xr-x 11 cabox cabox 4.0K Apr 10 21:06 ..                                  
drwxrwxr-x  8 cabox cabox 4.0K Apr 10 21:06 .git                                
-rw-rw-r--  1 cabox cabox 1.1K Apr 10 21:06 LICENSE                             
-rw-rw-r--  1 cabox cabox 1.4K Apr 10 21:06 README.md                           
drwxrwxr-x  7 cabox cabox 4.0K Apr 10 21:06 challenge_files                     
-rw-rw-r--  1 cabox cabox 5.5K Apr 10 21:06 nix_scavenger_hunt.md               
-rw-rw-r--  1 cabox cabox  317 Apr 10 21:06 nix_scavenger_hunt_stretch.md

* The `man` ("manual") command tells you more about how any given command works. (*WARNING:* CodeAnywhere does not support the man command. You can click the following link to complete this task: http://linux.die.net/man/)Run `man` to see instructions about how to use `man`. Then use `man` to learn what the `a`, `l`, and `h` options mean when used with the `ls` command. *Write down what those options do?*

a:"By default, man will exit after displaying the first manual page it finds. Using this option forces man to display all the manual pages that match name, not just the first."
l:"Suppress pause after form feed"
h:"Print a help message and exit."

* Commands can also take *arguments*, which are usually the names of files or locations that you want the command to work with. Try running `ls /` to see what files are in the *root* directory of the filesystem. *What files and directories do you see listed?*

bin   dev  fastboot  lib    media  opt   root  sbin  sys  usr                   
boot  etc  home      lib64  mnt    proc  run   srv   tmp  var 

* A Unix filesystem has a few special shortcuts to refer to specific locations. `/` indicates the *root* of the filesystem, meaning the top-most directory in the filesystem hierarchy. Use the `cd` ("change directory") command to move to the root directory. (Hint: Use `man` to look up the `cd` command if you have any issues) *Then run `pwd` and paste the output here:*

/home/cabox 

* Another special shortcut in Unix is the `~` location. This indicates the *user root* directory, meaning the top-most directory in the hierarchy that comes below your user account. Use `cd` to move to `~`. *Run `pwd` and paste the response here:*

-bash: /home/cabox: Is a directory 

* Change directory into the `challenge_files` directory. Use `ls` to find only the files with a `.demo` pattern. *How many files do you find?*

3

* Use the `cd` command to move "up" one directory. *Where are you in the filesystem now?*


* Press the up arrow on your keyboard. *What just happened?*

My previous command came up.

* Press the up arrow a few more times. *What do you see?*

It scrolled through my previous commands.

* Run the `history` command. *What do you see?*

A list of my past commands.

### Observing the System

* Discover what account you are logged into using the `whoami` command. *What username are you currently using?*

cabox

* Discover who else is on your system with the `who` command. *Are any other users using your system? If so, list them here:*

cabox    pts/0        Apr 10 22:07 (54.186.244.104)                             
cabox    pts/1        Apr 10 22:07 (54.186.244.104) 

* How long has your system been running? Use `uptime` to see, and *paste the result here:*

23:03:52 up  1:57,  2 users,  load average: 0.00, 0.00, 0.00 

* Run `ps aux` and review the results. (Hint: Use `man` to learn more about the `ps` command and options.) *How do you interpret what you see here?*

USER       PID %CPU %MEM    VSZ   RSS TTY      STAT START   TIME COMMAND        
root         1  0.0  0.4  33200  2560 ?        Ss   21:06   0:00 init           
root         2  0.0  0.0      0     0 ?        S    21:06   0:00 [kthreadd/60656
root         3  0.0  0.0      0     0 ?        S    21:06   0:00 [khelper/606569
root       149  0.0  0.1  19428   824 ?        S    21:06   0:00 upstart-udev-br
root       166  0.0  0.2  49216  1416 ?        Ss   21:06   0:00 /lib/systemd/sy
syslog     318  0.0  0.2 184188  1444 ?        Ssl  21:06   0:00 rsyslogd       
root       402  0.0  0.5  61316  3076 ?        Ss   21:06   0:00 /usr/sbin/sshd 
root       416  0.0  0.1  15492   844 ?        S    21:06   0:00 upstart-file-br
root       424  0.0  0.1  15600   992 ?        S    21:06   0:00 upstart-socket-
root       465  0.0  0.5  71260  2652 ?        Ss   21:06   0:00 /usr/sbin/apach
www-data   468  0.0  0.4 415720  2420 ?        Sl   21:06   0:02 /usr/sbin/apach
www-data   469  0.0  0.4 415720  2424 ?        Sl   21:06   0:02 /usr/sbin/apach
root       532  0.0  0.1  12740   852 tty1     Ss+  21:06   0:00 /sbin/getty 384
root       534  0.0  0.1  12740   856 tty2     Ss+  21:06   0:00 /sbin/getty 384
root       772  0.0  0.6  63876  3488 ?        Ss   22:07   0:00 sshd: cabox [pr
root       773  0.0  0.6  63876  3488 ?        Ss   22:07   0:00 sshd: cabox [pr
cabox      776  0.0  0.2  63876  1468 ?        S    22:07   0:00 sshd: cabox@pts
cabox      777  0.0  0.2  63876  1468 ?        S    22:07   0:00 sshd: cabox@pts
cabox      778  0.0  0.8  20560  4480 pts/0    Ss   22:07   0:00 -bash          
cabox      788  0.0  0.8  20560  4452 pts/1    Ss+  22:07   0:00 -bash          
root      1180  0.0  0.6  63876  3344 ?        Ss   22:22   0:00 sshd: cabox [pr
cabox     1182  0.0  0.2  64008  1504 ?        S    22:22   0:00 sshd: cabox@not
cabox     1183  0.0  0.1  12916   988 ?        Ss   22:22   0:00 /usr/lib/openss
cabox     1205  0.0  0.2  15520  1144 pts/0    R+   23:04   0:00 ps aux 

It appears to be a list of the users and commands that have been run.

* Run `top` and review the results. (Hint: You may need to use `ctrl-c` to get out of this app.) *How do you interpret what you see here?*

It looks like a real time list of the psaux results.
### Finding and Viewing Files

* Make sure you are in the `challenge_files` directory. Use the `*` wildcard to find all the files that have the word "credit" in the filename. *How many files did you find?*
* Use the `more` command to view one of the `credit_cards` files you just discovered. (Hint: Type `q` to quit viewing the file. Press the `spacebar` to page down. Use your keyboard arrows to move up/down.) *What is the date in the file you have viewed?*
* Use the `find` command to search for files more effectively. Search the sub-directories under `challenge_files` to find the location of the file named `modi_laboriosam.txt`. *Where is that file located?*
* Use the `grep` command to search for text within a file. Use `grep` on all the `.user` files in `challenge_files` to find which files contain "WA" (the abbreviation for Washington state). *How many files did you find?*
* Use the `-r` option of `grep` to *recursively* find the text "Waldo" hidden in a file somewhere under the `challenge_files` directory. *Paste the result showing the file and line where the word "Waldo" shows up.*

### Pipes and Connecting Commands

* Sometimes it's useful to output the results of a command to a text file for further analysis, reference, or processing. Try running `ls > files.txt`. Notice that the file `files.txt` was created. View that file using `more`. *What do you see in the `files.txt` file?*

Options:                                                        
  -d        display help instead of ring bell                   
  -f        count logical, rather than screen lines             
  -l        suppress pause after form feed                      
  -p        suppress scroll, clean screen and disblay text      
  -c        suppress scroll, display text and clean line ends   
  -u        suppress underlining                                
  -s        squeeze multiple blank lines into one               
  -NUM      specify the number of lines per screenful           
  +NUM      display file beginning from line number NUM         
  +/STRING  display file beginning from search string match     
  -V        output version information and exit 
  
* Notice that if you run `ls -alh` in the `challenge_files` directory, the files scroll by very quickly. Sometimes it would be better to get the results in a paginated format. Try running `ls -alh | more`. *Describe what you see when you run `ls -alh | more`.*

There are columns of directories, dates, and users.


* Earlier, when you viewed the list of active processes on your devbox using `ps aux`, the list was probably really long. You can make this list more manageable by using the pipe (`|`) to filter the results of `ps` using `grep`. Run `ps aux | grep <your_username>` to see what processes are running for your specific user. *Paste the list of processes that reference your username here:*

Error code including 'unexpected token 'newline''
