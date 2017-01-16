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
//I am working in codeanywhere as I am using a windows pc currently. Inside the ssh terminal opened under this connection from git; my pwd command output: /home/cabox/workspace

* Discover more about this filesystem. Use `ls` (the "list" command)to see what is in this directory. 
//The files that showed up were the files found with this repository on github. They are: LICENSE  README.md  challenge_files  nix_scavenger_hunt.md  nix_scavenger_hunt_stretch.md

* You can use *options* to modify how a command runs. Try using `ls -alh` to see the contents of your current directory. 
//This is really quite different it shows not just the file names, but also the file size, when it was last updated and the name. total 36K                                                                                                                                         
drwxrwxr-x  4 cabox cabox 4.0K Jan 15 20:08 .                                                                                                     
drwxr-xr-x 11 cabox cabox 4.0K Jan 15 20:08 ..                                                                                                    
drwxrwxr-x  8 cabox cabox 4.0K Jan 15 20:08 .git                                                                                                  
-rw-rw-r--  1 cabox cabox 1.1K Jan 15 20:08 LICENSE                                                                                               
-rw-rw-r--  1 cabox cabox 2.7K Jan 15 20:08 README.md                                                                                             
drwxrwxr-x  7 cabox cabox 4.0K Jan 15 20:08 challenge_files                                                                                       
-rw-rw-r--  1 cabox cabox 5.5K Jan 15 20:08 nix_scavenger_hunt.md                                                                                 
-rw-rw-r--  1 cabox cabox  317 Jan 15 20:08 nix_scavenger_hunt_stretch.md 

* The `man` ("manual") command tells you more about how any given command works. (*WARNING:* CodeAnywhere does not support the man command. You can click the following link to complete this task: http://linux.die.net/man/). Run `man` to see instructions about how to use `man`. Then use `man` to learn what the `a`, `l`, and `h` options mean when used with the `ls` command. 
//Since I am using CA I looked up the commands on linux.die.net. It's an almost dizzing amount of commands on that site, but the one's I am looking up were very easy to find under ls. The --a/ --all command means: do not ignore entries starting with " ". I am listing l before h because h pairs with l so the --l command does: use a long listing format. The --h/--human-readable command works as: with -l, print sizes in human readable format (e.g., 1K 234M 2G)

* Commands can also take *arguments*, which are usually the names of files or locations that you want the command to work with. Try running `ls /` to see what files are in the *root* directory of the filesystem. 
//I could see this being a lot bigger of an answer if I were running this command on an operating system. I know that most of these commands are suppose to be run inside of a folder or set of files. So for the smaller CA the following files appeared: bin  boot  dev  etc  fastboot  home  lib  lib64  media  mnt  opt  proc  root  run  sbin  srv  sys  tmp  usr  var

* A Unix filesystem has a few special shortcuts to refer to specific locations. `/` indicates the *root* of the filesystem, meaning the top-most directory in the filesystem hierarchy. Use the `cd` ("change directory") command to move to the root directory. (Hint: Use `man` to look up the `cd` command if you have any issues) 
// I initially ran cd / and then I ran the pwd command. This output "/" as the directory. Then after double checking by trying / cd immediately after I was told: -bash: /: Is a directory. Then pwd displayed the output "/" again.

* Another special shortcut in Unix is the `~` location. This indicates the *user root* directory, meaning the top-most directory in the hierarchy that comes below your user account. Use `cd` to move to `~`. 
// So this time I ran the command as cd ~ then went straight into the pwd, but first I made sure to google the cd command. The reason for this was to double check how I should structure these commands. I found this awesome website with examples of cd commands in linux http://www.tecmint.com/cd-command-in-linux/. For the results of my commands I did notice that my cabox@box-codeanywhere:~$ changed to ~$ vs /$. I also got /home/cabox from my pwd command.

* Change directory into the `challenge_files` directory. Use `ls` to find only the files with a `.demo` pattern. *How many files do you find?*
//To do this challenge I thought I had to do a cd change to /. Then I realized I still wasn't in the right directory so I went and looked at my older outputs and did the cd command to ~/workspace/. Which then allowed me to go to challenge files directory. I ran into a lot of issues trying to figure out the command that would work here and I finally found it at this web page https://askubuntu.com/questions/39200/how-to-search-for-files-containing-specific-word. Overall I found 3 .demo files after using the grep -R {.demo} command.

* Use the `cd` command to move "up" one directory. *Where are you in the filesystem now?*
//I initially tried cd up and nothing happened so then I just did cd and was taken to cabox@box-codeanywhere:~$

* Press the up arrow on your keyboard. *What just happened?*
//I was taken to the cd command

* Press the up arrow a few more times. *What do you see?*
//I was taken to cd up then to ls demo. So the arrow keys take you to previous commands that way you can sort of backtrack through your commands and filesystems

* Run the `history` command. *What do you see?*
//This is like looking at your history tab on your web browser. It allows you to see all your previous commands raw.


### Observing the System

* Discover what account you are logged into using the `whoami` command. *What username are you currently using?*
I am cabox

* Discover who else is on your system with the `who` command. *Are any other users using your system? If so, list them here:*
cabox    pts/0        Jan 15 22:28 (54.186.244.104) This is an ip from Oregon                                                                                              
cabox    pts/1        Jan 15 22:29 (54.69.152.243) This is CA's ip

* How long has your system been running? Use `uptime` to see, and *paste the result here:*
22:39:26 up  2:31,  2 users,  load average: 0.00, 0.00, 0.00 so 2 hours with 2 users

* Run `ps aux` and review the results. (Hint: Use `man` to learn more about the `ps` command and options.) *How do you interpret what you see here?*
It seems to be basic operating data such as what threads are running and how resource intensive they are.
USER       PID %CPU %MEM    VSZ   RSS TTY      STAT START   TIME COMMAND                                                                          
root         1  0.0  0.4  33196  2512 ?        Ss   20:08   0:00 init                                                                             
root         2  0.0  0.0      0     0 ?        S    20:08   0:00 [kthreadd/918946]                                                                
root         3  0.0  0.0      0     0 ?        S    20:08   0:00 [khelper/918946]                                                                 
root       151  0.0  0.1  19428   820 ?        S    20:08   0:00 upstart-udev-bridge --daemon                                                     
root       168  0.0  0.2  49216  1396 ?        Ss   20:08   0:00 /lib/systemd/systemd-udevd --daemon                                              
syslog     315  0.0  0.2 184188  1448 ?        Ssl  20:08   0:00 rsyslogd                                                                         
root       353  0.0  0.1  15360   688 ?        S    20:08   0:00 upstart-file-bridge --daemon                                                     
root       354  0.0  0.1  15472   924 ?        S    20:08   0:00 upstart-socket-bridge --daemon                                                   
root       404  0.0  0.5  61316  3076 ?        Ss   20:08   0:00 /usr/sbin/sshd -D                                                                
root       460  0.0  0.5  71260  2652 ?        Ss   20:08   0:00 /usr/sbin/apache2 -k start                                                       
www-data   463  0.0  0.4 415720  2420 ?        Sl   20:08   0:03 /usr/sbin/apache2 -k start                                                       
www-data   464  0.0  0.4 415720  2424 ?        Sl   20:08   0:03 /usr/sbin/apache2 -k start                                                       
root       527  0.0  0.1  12740   856 tty1     Ss+  20:08   0:00 /sbin/getty 38400 console                                                        
root       529  0.0  0.1  12740   852 tty2     Ss+  20:08   0:00 /sbin/getty 38400 tty2                                                           
root       779  0.0  0.6  63876  3476 ?        Ss   22:27   0:00 sshd: cabox [priv]                                                               
cabox      781  0.0  0.2  63876  1464 ?        S    22:27   0:00 sshd: cabox@pts/0                                                                
cabox      782  0.0  0.8  20632  4556 pts/0    Ss+  22:27   0:00 -bash                                                                            
root       979  0.0  0.6  63876  3476 ?        Ss   22:29   0:00 sshd: cabox [priv]                                                               
cabox      981  0.0  0.2  63876  1464 ?        S    22:29   0:00 sshd: cabox@pts/1                                                                
cabox      982  0.0  0.8  20632  4560 pts/1    Ss   22:29   0:00 -bash                                                                            
cabox     1182  0.0  0.2  15520  1144 pts/1    R+   22:40   0:00 ps aux                     

* Run `top` and review the results. (Hint: You may need to use `ctrl-c` to get out of this app.) *How do you interpret what you see here?*
This looks like an in-line version on crtl+alt+delete's resource tab. It shows programs running in real time and the amount of loss vs uptime.


### Finding and Viewing Files

* Make sure you are in the `challenge_files` directory. Use the `*` wildcard to find all the files that have the word "credit" in the filename. *How many files did you find?* 
//I was finally able to figure out the command to use thanks to https://askubuntu.com/questions/39200/how-to-search-for-files-containing-specific-word. I found two credit cards.txt files.

* Use the `more` command to view one of the `credit_cards` files you just discovered. (Hint: Type `q` to quit viewing the file. Press the `spacebar` to page down. Use your keyboard arrows to move up/down.) *What is the date in the file you have viewed?*
//These are all the credit card numbers for the various .user files.

* Use the `find` command to search for files more effectively. Search the sub-directories under `challenge_files` to find the location of the file named `modi_laboriosam.txt`. *Where is that file located?*
//It was under the tmp folder inside of the challenge files. I had to look the command up at this website http://www.howtogeek.com/112674/how-to-find-files-and-folders-in-linux-using-the-command-line/

* Use the `grep` command to search for text within a file. Use `grep` on all the `.user` files in `challenge_files` to find which files contain "WA" (the abbreviation for Washington state). *How many files did you find?*
//All I recieve is a list of all the files in the challenge file. I seem to be unable to get grep to search as I keep being told that no such files or directory exisit for .user.

* Use the `-r` option of `grep` to *recursively* find the text "Waldo" hidden in a file somewhere under the `challenge_files` directory. *Paste the result showing the file and line where the word "Waldo" shows up.*
//Once again I am unable to get grep to show me any information.

### Pipes and Connecting Commands

* Sometimes it's useful to output the results of a command to a text file for further analysis, reference, or processing. Try running `ls > files.txt`. Notice that the file `files.txt` was created. View that file using `more`. *What do you see in the `files.txt` file?*
// Everything in the files.txt was the .demo files, the .user, the .txt, and the folders. Which is the base folder of challenge files.

* Notice that if you run `ls -alh` in the `challenge_files` directory, the files scroll by very quickly. Sometimes it would be better to get the results in a paginated format. Try running `ls -alh | more`. *Describe what you see when you run `ls -alh | more`.*
//I see the users names in a more top to bottom order that is easier to read/see the differences. This would make it easier to pick out a single file if you were looking a specific file.

* Earlier, when you viewed the list of active processes on your devbox using `ps aux`, the list was probably really long. You can make this list more manageable by using the pipe (`|`) to filter the results of `ps` using `grep`. Run `ps aux | grep <your_username>` to see what processes are running for your specific user. *Paste the list of processes that reference your username here:*
//cabox     1586  0.0  0.1  63876   844 ?        S    Jan15   0:00 sshd: cabox@pts/0                                                                
cabox     1587  0.0  0.2  20632  1560 pts/0    Ss+  Jan15   0:00 -bash                                                                            
root      1784  0.0  0.5  63876  2732 ?        Ss   Jan15   0:00 sshd: cabox [priv]                                                               
cabox     1786  0.0  0.1  64008   864 ?        S    Jan15   0:02 sshd: cabox@pts/1                                                                
cabox     1787  0.0  0.3  20632  1848 pts/1    Ss   Jan15   0:00 -bash                                                                            
root      1999  0.0  0.5  63876  2728 ?        Ss   Jan15   0:00 sshd: cabox [priv]                                                               
root      2000  0.0  0.5  63876  2736 ?        Ss   Jan15   0:00 sshd: cabox [priv]                                                               
cabox     2003  0.0  0.1  63876   840 ?        S    Jan15   0:00 sshd: cabox@pts/2                                                                
cabox     2004  0.0  0.1  63876   844 ?        S    Jan15   0:00 sshd: cabox@pts/3                                                                
cabox     2005  0.0  0.5  20632  3140 pts/2    Ss+  Jan15   0:00 -bash                                                                            
cabox     2191  0.0  0.6  20632  3416 pts/3    Ss+  Jan15   0:00 -bash                                                                            
cabox     2404  0.0  0.2  15520  1144 pts/1    R+   00:49   0:00 ps aux