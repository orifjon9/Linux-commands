# Linux command line cheat sheet

## Basic

| Command | Description                                                                   |
| ------- | ----------------------------------------------------------------------------- |
| **pwd** | displays the full path to the current directory (folder)                      |
| **cd**  | change a directory                                                            |
|         | `cd /` changes a directory to root                                            |
|         | `cd /home` or `cd ~` changes a directory to a home as absolute path           |
|         | `cd orifjon` or `cd ./orifjon` change a directory that in a current directory |
|         | `cd ..` change a directory to a parent directory                              |
|         | Note                                                                          |
|         | `./` currect directory                                                        |
|         | `../` up or parent directory                                                  |
|         | `/` root directory directory                                                  |
|         | `~` home directory                                                            |
| **ls**  | shows all details and list of directory and files in a current directory      |
|         | `ls` list of directory and files in a current directory                       |
|         | `ls -l` more information                                                      |
|         | `ls -r` reverse order                                                         |
|         | `ls -lr` or `ls -l -r` more an reverse order list                             |
|         | `ls -p` type                                                                  |
|         | `ls -s` sort                                                                  |
|         | `ls ~/Documents -r -d`                                                        |
|         | `ls --help` List information                                                  |

&nbsp;

## Administrative privileges

| Permissions | Commands example   |
| ----------- | ------------------ |
| U -- G -- W |                    |
| rwx rwx rwx | chmod 777 file.txt |
| rwx rwx r-x | chmod 775 file.txt |
| rwx r-x r-x | chmod 755 file.txt |
| rw- rw- r-- | chmod 664 file.txt |
| rw- r-- r-- | chmod 644 file.txt |

    U = User
    G = Group
    W = World

    r = Read
    w = write
    x = execute
    - = no access

![linux permissions chart](images/linux-permissions-chart.png)

## Package manager (apt-get) to install new applications

| Command                     | Description                                                                                      |
| --------------------------- | ------------------------------------------------------------------------------------------------ |
| **apt-get upgrade**         | updates all installed app to latest                                                              |
| **apt-get install**         | install an application                                                                           |
|                             | `apt-get install gimp` installs gimp                                                             |
| **apt-get remove**          | uninstall an application                                                                         |
|                             | `apt-get removes bluefish` removes bluefish                                                      |
| **apt-cache search**        | searches installed an application                                                                |
|                             | `apt-cache search bluefish` searches installed bluefish application                              |
| **apt-cache policy search** | provides info for an application and build version                                               |
|                             | `apt-cache policy bluefish` policy for bluefish app                                              |
| **dpkg**                    | install an app if you have a source .deb                                                         |
|                             | `dpkg -i /home/downloads/chrome-browser.deb` installs chrome-browser.deb source in local machine |

## File permissions and ownership

| Permissions | Commands example                                                                      |
| ----------- | ------------------------------------------------------------------------------------- |
| **chown**   | Update a file ownership                                                               |
|             | `chown user:group file`                                                               |
|             | `chown root:orifjon9 admin.txt` orifjon9 will get an access as a group bot not own it |
|             | `chown orifjon9:orifjon9 admin.txt` orifjon9 is owns and access as group              |
|             | `chown -R orifjon9:orifjon9 /usr/www` take an ownership to all file recursively       |
| **chmod**   | Updates a file permission                                                             |
|             | `chmod 664 admin.txt` set a new permission                                            |

## Manage directories and files

| Permissions | Commands example                                                  |
| ----------- | ----------------------------------------------------------------- |
| **ls**      | `ls -al` List all files in a long listing (detailed) format       |
| **touch**   | Create file(s)                                                    |
|             | `touch test.txt test.txt` create files                            |
|             | `echo "test test" > test2.txt` create files                       |
| **rm**      | removes file(s)                                                   |
|             | `rm test.txt` create                                              |
|             | `rm ./mydir/test.txt` or `rm ./mydir/*.txt` or `rm ./mydir/*`     |
|             | `rm -rf ./mydir/` remove a directory                              |
|             | `rm -r ./mydir` Remove the directory and its contents recursively |
| **mkdir**   | Create a directory                                                |
|             | `mkdir mydir`                                                     |
| **mv**      | move a file or folder                                             |
|             | `mv test.txt ./mydir/test.txt` or `mv test.* ./mydir`             |
|             | `mv test.txt test.txt` renames a file                             |
| **cp**      | copy a file or folder                                             |
|             | `cp test.txt ./mydir/test.txt` copy a file                        |
| **cat**     | `cat test.txt` view the content                                   |
| **less**    | `less test.txt` Browse through a text file                        |
| **head**    | `head test.txt` Display the first 10 lines of file                |
| **tail**    | `tail test.txt` Display the last 10 lines of file                 |

## Search

| Permissions | Commands example                                                                |
| ----------- | ------------------------------------------------------------------------------- |
| **find**    | `find directory -type {f file d directory} -name name`                          |
|             | `find . -type f -name "admin.txt"`                                              |
|             | `find . -type f -not -name "*.txt"` not txt files                               |
|             | `find . -type f -name "*.txt"`                                                  |
|             | `find . -type d -name "admin*"` searches directories starts with admin          |
|             | `find /etc -type f -iname "*.txt"` ignores case intensive                       |
|             | `find /etc -maxdepth 1 -type f -iname "*.conf"` control recursive               |
|             | `find /etc -type f -perm 0664` search files with asked permission               |
|             | `find . -size +1M` or `find . -size -1M` search files with over or less 1mb     |
| **grep**    | `grep -i -n "function" test.txt test.txt` search files contains asked text      |
|             | `find . -type f -iname "*.txt" -exec grep -i -n "function" {} +`                |
|             | `find . -type f -iname "*.txt" -exec grep -i -n "function" {} + | tee result.txt` |
