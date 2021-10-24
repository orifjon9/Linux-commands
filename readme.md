# Linux command line cheat sheet

## Basic
| Command | Description |
| ----------- | ----------- |
| **pwd** | displays the full path to the current directory (folder) |
| **cd** | change a directory |
|| `cd /` changes a directory to root|
|| `cd /home` or `cd ~` changes a directory to a home as absolute path |
|| `cd orifjon` or `cd ./orifjon` change a directory that in a current directory |
|| `cd ..` change a directory to a parent directory |
||Note|
||`./` currect directory|
||`../` up or parent directory|
||`/` root directory directory|
||`~` home directory|
|**ls**|shows all details and list of directory and files in a current directory|
||`ls` list of directory and files in a current directory|
||`ls -l` more information|
||`ls -r` reverse order|
||`ls -lr` or `ls -l -r` more an reverse order list|
||`ls -p` type|
||`ls -s` sort|
||`ls ~/Documents -r -d` |
||`ls --help` List information |
&nbsp;

## Administrative privileges


| Permissions | Commands example
|---------|-----------|
| U   G   W | | 
|rwx rwx rwx |    chmod 777 file.txt |
|rwx rwx r-x |    chmod 775 file.txt |
|rwx r-x r-x |    chmod 755 file.txt |
|rw- rw- r-- |    chmod 664 file.txt |
|rw- r-- r-- |   chmod 644 file.txt |

    U = User
    G = Group
    W = World

    r = Read
    w = write
    x = execute
    - = no access

![linux permissions chart](images/linux-permissions-chart.png)


## Package manager (apt-get) to install new applications

| Command | Description |
| ----------- | ----------- |
| **apt-get upgrade** | updates all installed app to latest  |
| **apt-get install** | install an application  |
||`apt-get install gimp` installs gimp |
| **apt-get remove** | uninstall an application  |
||`apt-get removes bluefish` removes bluefish |
| **apt-cache search** | searches installed an application  |
||`apt-cache search bluefish` searches installed bluefish application |
| **apt-cache policy search** | provides info for an application and build version  |
||`apt-cache policy bluefish` policy for bluefish app |
|**dpkg**| install an app if you have a source .deb|
||`dpkg -i /home/downloads/chrome-browser.deb` installs chrome-browser.deb source in local machine|

## File permissions and ownership 

| Permissions | Commands example
|---------|-----------|
| **chown**| Update a file ownership | 
| | `chown user:group file` | 
| | `chown root:orifjon9 admin.txt` orifjon9 will get an access as a group bot not own it | 
| | `chown orifjon9:orifjon9 admin.txt` orifjon9 is owns and access as group| 
| **chmod**| Updates a file permission | 
| | `chmod 664 admin.txt` set a new permission | 