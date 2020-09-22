# useful-linux-command-lines
### Change corrent directory to shrter type 
#### It is in ~/.bashrc but you can test is with this
``` export PS1="\u > " ```
* Instead of \u you can use this things
```
\a     The 'bell' character
\A     24h Time
\d     Date (e.g. Tue Dec 21)
\e     The 'escape' character
\h     Hostname (up to the first ".")
\H     Hostname
\j     No. of jobs currently running (ps)
\l     Current tty
\n     Line feed
\t     Time (hh:mm:ss)
\T     Time (hh:mm:ss, 12h format)
\r     Carriage return
\s     Shell (i.e. bash, zsh, ksh..)
\u     Username
\v     Bash version
\V     Full Bash release string
\w     Current working directory
\W     Last part of the current working directory
\!     Current index in history
\#     Command index
\$     A "#" if you're root, else "$"
\\     Literal Backslash
\@     Time (12h format with am/pm
```

### How to find does each port in used or not 
```
netstate -na | LISTEN
```
### How forward your internet to remote server by ssh
![quid architecture](/pics/squid.png)
```
ssh -L 3128:127.0.0.1:3128 user@10.XXX.XXX.XXX
export http_proxy=http://127.0.0.1:3129(3128)
export http_proxy=http://127.0.0.1:3129(3128)
```
### Unzip multiple files using shell for loop
```
for g in *.gz; do gunzip $g; done
```

### To create a directory path that is not exist your can use '-p' switch
```
mkdir -p /vol/web/media
mkdir -p /vol/web/static
```
### chown -R meanse recursive that meanes all sub directory contain, and in user:user firs user is user and the second is groupid that you can see it in ll
### To see resource file of grep result use this
```
grep LN * (grep LN *)
LN : Lorestan 
```
---------------------------------------

### TO get multiple files in ftp path
```
 Run this first:

  prompt noprompt

 So run this to get all files

  mget files(*.csv)
```

### It's how to kill all running tmux or all tmux instead of current session
```
# kill all tmux
pkill -f tmux
# remove all session except current session
tmux kill-session -a
```
