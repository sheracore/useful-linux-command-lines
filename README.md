# useful-linux-command-lines
### Change corrent directory in terminal
#### It is in ~/.bashrc but you can test it with this command lines without changing bashrc
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

#### How to find does each port in used or not 
```
netstate -na | LISTEN
```
##### To find port connection
```
nc -vz 192.168.15.72 22
```

#### Unzip multiple files using shell for loop
```
for g in *.gz; do gunzip $g; done
```

#### To create a directory path that is not exist you can use '-p' switch
```
mkdir -p /vol/web/media
mkdir -p /vol/web/static
```
#### chown -R meanse recursive that meanes all sub directory contain, and in user:user firs user is user and the second is groupid that you can see it in ll

## FTP
#### To get multiple files in ftp path
```
 Run this first:

  prompt noprompt

 So run this to get all files

  mget files(*.csv)
```

## Tmux
#### It's how to kill all running tmux or all tmux instead of current session
```
# kill all tmux
pkill -f tmux
# remove all session except current session
tmux kill-session -a

control + b  and  < ----> rename
control + b  and  c ----> new window
control + b  and  z ----> zoom
control + b  and  " ----> separate screen horizontal
control + b  and  % ----> separate screen vertical
control + b  and  w ----> show all sessions
control + b  and  m ---->  mouse ON and insert it again to mouse OFF
```
## Grep
#### To see resource file of grep result use '-r or -lr' switch or just grep without 'ls | grep'
```
cat * | grep -r QN 
cat * | grep -lr QN
grep QN * (grep QN *)
QN : Qazvin 
```
#### How to grep multiple strings
```
grep -e patten1 -e pattern2 -e pattern3 
```
#### If you couldn's install psycopg2 on alpine docker, you can install these befor installing psycopg2
```
RUN apk update && apk add postgresql-dev gcc python3-dev musl-dev
pip install psycopg2
```

#### This command is like tail -f but this one you can use it for directories
```
watch ls
```

## Network
#### To show network status ports and Ip's listen
```
sudo netstat -tulpn | grep LISTEN
```

## find
#### To find type of file use this
```
find / -type f -name "*.py"
```

## Git
#### Delete local changes
```
git checkout -f
git clean -fd
or
git reset --hard
```
#### Untrack folder locally in git and push to production without deleting [Link](https://stackoverflow.com/questions/24290358/remove-a-folder-from-git-tracking)
```
git rm -r --cached --ignore-unmatch folder_name
```
#### Push commit message changes without any file changes
```
git push --force-with-lease origin example-branch
```

#### git pull/clone with deploy key
```
GIT_SSH_COMMAND='ssh -i private_key_file -o IdentitiesOnly=yes' git clone user@host:repo.git
GIT_SSH_COMMAND='ssh -i private_key_file -o IdentitiesOnly=yes' git pull
```

## Screen
#### To assign name to screen
```
screen -S your_session_name
```
#### To show list of screen
```
screen -ls
```
#### To go into the screen
```
screen -r [screen_name]
```
#### How to kill session
```
$ screen -X -S [session # you want to kill] quit
```
## Hardware
#### To monitoring use:
```
top
htop
```
#### To show free memory use:
```
free -m
free -mh
```
## dpkg
#### To install .deb softwares
```
sudo dpkg -i [software_name].deb
```
#### To change and reconfigure locals in deb
```
 export LC_ALL=en_US.UTF-8
 sudo  dpkg-reconfigure locales
```

## ls
```
lspci
lshw
lslok
lsns
```
## SSHUTTL
#### To transfer all traffic from your vps
```
sshuttle -r user@ip(VPS) -x ip(vps) 0/0
```
## SSH
#### To do ssh on your system by another host you shold open your ssh by
```
 sudo apt install openssh-server
```
#### To transfer your traffic in a specific port for using sucks5 like telegram uses the following command this should use by a foregin vps
```
ssh -D [any port] -N user@ip
telegram: sucks5 127.0.0.1:aboveport
browser: add on switch omega
```

#### Copy ssh_pub to a remote server in it's ~/.ssh/known_hosts
```
ssh-copy-id fwutech@192.168.181.26 -p 50001
```

#### How forward your internet to remote server by ssh
![quid architecture](/pics/squid.png)
```
ssh -L 3128:127.0.0.1:3128 user@10.XXX.XXX.XXX
export http_proxy=http://127.0.0.1:3128(3129)
export http_proxy=http://127.0.0.1:3128(3129)
```

#### So you shold allow to ssh by ufw
```
sudo ufw allow ssh
```
## Mount
#### how to mount windows drives in linux
```
sudo mount -t ntfs-3g -o ro /dev/sda4 /media/mohamad/WIN_PART/
OR
sudo mount -t vfat -o ro /dev/sdb1 /media/aaronkilik/WIN_PART
```
## tr
```
$cat greekfile | tr “[a-z]” “[A-Z]”
$cat geekfile | tr “[:lower:]” “[:upper:]”
$ echo "Welcome To GeeksforGeeks" | tr [:space:] '\t'
$ tr '{}' '()'   newfile.txt
$ echo "Welcome    To    GeeksforGeeks" | tr -s [:space:] ' '

```

## Add user and create sftp
### First create a group and so ..
```
sudo addgroup sftp
sudo useradd -m sftpuser -g sftp
sudo passwd sftpuser
sudo chmod 700 /home/sftpuser/
```

## Loop in linux 
```
$ for i in $( ls ); do mv $i $i.txt; done
for i in $( ls ); do mv "               $i" "SOURCE$i"; done
```

# Rust
## Create rustenv
### First install venv of python so install rustenv
```
virtualenv venv -p python3
source ./venv/bin/activate
pip3 install rustenv
rustenv renv
source renv/bin/activate 
```


