# TOOLS  

---

<br>

## GIT

<br>

---

<br>

<h4>Create a New Git Repository from scratch</h4>
```
mkdir to create a directory to contain the project.
cd into the new directory.
git init.
Write code. (The first file to create is probably a ReadMe file)
git add to add the files.
git commit
```

<br>

---

<br>

<h4>Create New Git Repository from existing project</h4>
```
cd into the directory containing the project.
git init.
git add to add all of the relevant files.
create a .gitignore to indicate all of the files you don’t want to track
git commit.
```

<br>

---

<br>

<h4>Connect to github</h4>
```
Go to github.
Log in to your account.
Click the new repository button in the top-right. 
Click the “Create repository” button.
git remote add origin git@github.com:username/new_repo
git push -u origin master
```

<br>

---

<br>

<h4>Create, switch and push origin new branch</h4>
```
git checkout -b issue400-master
git push -u origin issue400-master
```

<br>

---

<br>

<h4>Add, Commit and Push</h4>
```
git add sys_ui/css/FILE.css 
git add sys_ui/FILE.html 
git add app/dir/ 
git commit
git push
```

<br>

---

<br>

<h4>Delete a local and remote branch</h4>
```
git branch -d branch_name
git push origin --delete <branch_name>
```

<br>

---

<br>

<h4>Remove cached files</h4>
```
git rm -r --cached .
git add .
git commit -m "fixed untracked files"
```

<br>

---

<br>

<h4>Clean Local branch</h4>
```
git reset
git checkout .
git clean -fdx
```

<br>

---

<br>

<h4>Clone repo</h4>
```
git clone USER@10.0.2.10:/home/git/repos/sys .
```

<br>

---

<br>

<h4>Clone specific branch</h4>
```
git clone -b <branch> <remote_repo>
git clone -b my-branch git@github.com:user/myproject.git
```

<br>

---

<br>

<h4>Show current branch</h4>
```
git branch
```

<br>

---

<br>

<h4>Show local and remote branch</h4>
```
git branch -a
```

<br>

---

<br>


<h4>Check Status</h4>
```
git status
```

<br>

---

<br>

<h4>Check Log</h4>
```
git log
```

<br>

---

<br>


<h4>Graphical Log</h4>
```
git log --graph --decorate
```

<br>

---

<br>

<h4>Log commit subject of last 10 commits</h4>
```
git log -10 --pretty=format:"%h %s"
```

<br>

---

<br>

<h4>Edit Last Commit Message</h4>
```
git commit --amend -m "New commit message"
```

<br>

---

<br>

<h4>Single file history</h4>
```
git log -p filename
```

<br>

---

<br>

<h4>Get tag</h4>
```
git log --decorate v0.4bugfix|head -n1|sed 's/.*tag: //;s/[^a-zA-Z.0-9].*//'
```

<br>

---

<br>

<h4>Get commits by date and author</h4>
```
git log --pretty=format:"%ad - %an: %s" --after="2010-02-15" --until="2018-08-20" --author="John"
```

<br>

---

<br>

<h4>Get number of commits by author</h4>
```
git shortlog -s -n --all
```

<br>

---

<br>

<h4>Remove local untracked files</h4>
```
git clean -fdx
```

<br>

---

<br>

<h4>Undo last commit.</h4>
Warning: Don't do this if you've already pushed
```
git reset HEAD~
```

<br>

---

<br>

<h4>Undo last commit.</h4>
If you don't want the changes and blow everything away:
Warning: Don't do this if you've already pushed
```	
git reset --hard HEAD~
```

<br>

---

<br>

<h4>Untrack .pyc files</h4>
```
$ find . -name '*.pyc' | xargs -n 1 git rm --cached
```

<br>

---

<br>

<h4>Switch to branch</h4>
```
git checkout BRANCHNAME
```

<br>

---

<br>

<h4>Pull from master branch</h4>
```
git pull origin master
```

<br>

---

<br>

<h4>Checkout master</h4>
```
git chekcout master
```

<br>

---

<br>

<h4>Merge branch into master</h4>
```
git checkout master
git merge user_interface
```

<br>

---

<br>

<h4>Rebase</h4>
git-rebase - Reapply commits on top of another base tip
```
git checkout branchname
git rebase master
```

In case of conflicts, fix them and then:
```
git add namefile.jsx
git rebase --continue
```

<br>

---

<br>

<h4>Create Tags</h4>
```
git tag v1.0 ec32d32
git push origin --tags
```

<br>

---

<br>

<h4>Undo a local commit</h4>
```
git reset --soft HEAD^     # use --soft if you want to keep your changes
git reset --hard HEAD^     # use --hard if you don't care about keeping the changes you made
```

<br>

---

<br>

<h4>Undo git add</h4>
```
git reset filename.jsx
```

<br>

---

<br>

<h4>Make a copy of local branch</h4>
```
git checkout old_branch
git branch new_branch
```

<br>

---

<br>

<h4>Show differences after git pull</h4>
```
git diff master@{1} master
```

<br>

---

<br>

<h4>Lists branches merged into master</h4>
```
git branch --merged master
```

<br>

---

<br>

<h4>Lists branches merged into HEAD</h4>
```
git branch --merged 
```

<br>

---

<br>

<h4>Lists branches that have not been merged</h4>
```
git branch --no-merged
```

<br>

---

<br>

<h4>Checkout previous branch</h4>
```
git checkout -
```

<br>

---

<br>

<h4>Diff between branches</h4>
Diff between current branch and master:  
```
git diff master
```

<br>

---

<br>

<h4>Diff between two branches:</h4>
```
git diff master..staging
```

<br>

---

<br>

<h4>Show only files that are different between the two branches</h4>
```
git diff --name-status master..staging
```

<br>

---

<br>

<h4>Create New Branch and Checkout – In One Command</h4>
```
git checkout -b <branch_name>
```

<br>

---

<br>

<h4>Revert Changes to File</h4>
```
git checkout -- <file>
```

<br>

---

<br>

<h4>Squashing commits into one</h4>
To maintain a clean commit log message when merging the remote branch to master.

SCRIPT:
```
#!/bin/bash
#

#commits to squash
commitCount=$1

#get the commit message
shift
commitMessage=$@

#verify that squash number is an integer
regex='^[0-9]+$'

echo "---------------------------------"
echo "Will squash $commitCount commits"
echo "Commit message will be '$commitMessage'"

echo "...validating input"
if ! [[ $commitCount =~ $regex ]]
then
    echo "Squash count must be an integer."
elif [ -z "$commitMessage" ]
then
    echo "Invalid, sure string is not empty"
else
    echo "...input looks good"
    echo "...proceeding to squash"
    git reset --soft HEAD~$commitCount
    git commit -m "$commitMessage"
    echo "...done"
fi

echo
exit 0
```

Find directories being used in your path.  
```
echo $PATH
```
Pick a dir to put the script. For example “/home/name/bin”.  
Name script to “git-squash.sh”.  
Make the file executable “chmod +x file_name”  
Now create an alias for git. 
Run “ls -la /bin/sh” to find out the default shell. (e.g. dash)
Run “/bin/dash” to enter the shell and execute:  
```
git config --global alias.squash "!bash -c 'bash <path_of_script>/git-squash.sh \$1 \$2' -"  
```

USAGE:  
Squash n commits:  
```
git squash n 'my commit message'  
```

You can skip as many commits as you want by change the number after the --skip flag.
Combine the two commands to squash n amount of commits into one, with the specified commit message:
```
git squash n $(git log -n 1 --skip n --pretty=%B)
```

Now that the commit has been squashed into one, you can push to the remote branch on gitlab, by running this command:
```
git push --force origin <name_of_branch>
```

<br>

---

<br>

<h4>Git reset head</h4>
Force previous commit to become head.  
```
git reset --hard <COMMITID>
git push -f origin <BRANCH>
```



<br>

---

<br>



---

## LINUX TIPS

<br>

---

<br>

<h4>Systems Directories</h4>
```
/ The root directory.  
/bin Contains binaries (programs) that must be present for the system to boot and run.  
/boot Contains Linux kernel, initial RAM disk image, and the boot loader.
/dev This is a special directory which contains device nodes.  
/etc configuration files / shell scripts for system services at boot time.
/home each user is given a directory in /home
/lib Contains shared library files used by the core system
/lost+found used in the case of a partial recovery from a file system corruption event
/media mount points for removable media
/mnt On older Linux systems, mount points for removable devices
/opt to install “optional” software.
/proc virtual file system maintained by the Linux kernel
/root home directory for the root account.
/sbin “system” binaries. 
/tmp temporary files
/usr all the programs and support files used by regular users.
/usr/bin /usr/bin contains the executable programs installed by your Linux distribution
/usr/lib shared libraries for the programs in /usr/bin.
/usr/local programs that are not included with your distribution but are intended for systemwide use are installed.
/usr/sbin system administration programs.
/usr/share all the shared data used by programs in /usr/bin.
/usr/share/doc packages documentation.
/var where data that is likely to change is stored.
/var/log log files
```

<br>

---

<br>

<h4>Most used Commands</h4>
```
ls Directory listing
ls -al Formatted listing with hidden files
ls -lt Sorting the Formatted listing by time modification
cd dir Change directory to dir
cd Change to home directory
pwd Show current working directory
mkdir dir Creating a directory dir
cat >file Places the standard input into the file
more file Output the contents of the file
head file Output the first 10 lines of the file
tail file Output the last 10 lines of the file
tail -f file Output the contents of file as it grows,starting with the last 10 lines
touch file Create or update file
rm file Deleting the file
rm -r dir Deleting the directory
rm -f file Force to remove the file
rm -rf dir Force to remove the directory dir
cp file1 file2 Copy the contents of file1 to file2
cp -r dir1 dir2 Copy dir1 to dir2;create dir2 if not present
mv file1 file2 Rename or move file1 to file2,if file2 is an existing directory
ln -s file link Create symbolic link link to file
```
<br>

---

<br>

<h4>Process Management</h4>
```
ps To display the currently working processes
top Display all running process
kill pid Kill the process with given pid
killall proc Kill all the process named proc
pkill pattern Will kill all processes matching the pattern
bg List stopped or background jobs,resume a stopped job in the background
fg Brings the most recent job to foreground
fg n Brings job n to the foreground
```

<br>

---

<br>

<h4>File permission</h4>
```
chmod octal file Change the permission of file to octal,which can be found separately for user,group,world by adding,
• 4-read(r)
• 2-write(w)
• 1-execute(x)
```

<br>

---

<br>

<h4>How many lines for file extension</h4>
```
wc `find | grep jsx$`
```

<br>

---

<br>

<h4>List nested folders/files </h4>
```
tree -L 2
```

<br>

---

<br>

<h4>Find file</h4>
```
find /path/to/file/ -iname filename
```

<br>

---

<br>

<h4>Get differences between 2 folders</h4>
```
diff --brief --recursive dir1/ dir2/ # GNU long options
diff -qr dir1/ dir2/ # common short options
```

<br>

---

<br>

<h4>Grep with exclude</h4>
```
grep -r "moment" --exclude-dir=node_modules
```

<br>

---

<br>

<h4>Grep files names only</h4>
```
grep -rl "text" --exclude-dir=node_modules --exclude-dir=deploy --exclude-dir=.venv
```

<br>

---

<br>

<h4>Truncate file content</h4>
```
truncate -s 0 dash.txt
```

<br>

---

<br>

<h4>cat long file</h4>
```
cat branch | more -d
```

<br>

---

<br>

<h4>Check if port is listening</h4>
```
sudo netstat -ntlp | grep :443
```

<br>

---

<br>

<h4>Find a string</h4>
```
grep -r "test" - find string
```

Find string include, exclude, ignore case
```
grep -r -i ".ui" --include \*.scss --exclude app.scss
```

Find Large files
```
find / -size +10M -ls
```

<br>

---

<br>

<h4>Directory Size</h4>
```
du -hs direcotryName
```

<br>

---

<br>

<h4>Show system name and kernel</h4>
```
uname -a
```

<br>

---

<br>

<h4>Start a screen session</h4>
```
screen
```

<br>

---

<br>

<h4>Resume a screen session</h4>
```
screen -r
```

<br>

---

<br>

<h4>List screen sessions</h4>
```
screen -list
```

<br>

---

<br>

<h4>List All Available Packages</h4>
```
apt-cache pkgnames
```

<br>

---

<br>

<h4>Upgrade packages and Install git</h4>
```
sudo apt-get update
sudo apt-get upgrade
sudo apt-get install git
git --version
```

<br>

---

<br>

<h4>Package Name and Description of Software</h4>
```
apt-cache search vsftpd
```

<br>

---

<br>

<h4>Remove packages</h4>
```
sudo apt-get autoremove -y
```

<br>

---

<br>

<h4>Package Information</h4>
```
apt-cache show netcat
```

<br>

---

<br>

<h4>Dependencies for Specific Packages</h4>
```
apt-cache showpkg vsftpd
```

<br>

---

<br>

<h4>Update System Packages</h4>
```
sudo apt-get update
```

<br>

---

<br>

<h4>Clean up disks space</h4>
```
sudo apt-get clean
```

<br>

---

<br>

<h4>Download only source code</h4>
```
sudo apt-get --download-only source vsftpd
```

<br>

---

<br>

<h4>Check broken dependencies</h4>
```
sudo apt-get check
```

<br>

---

<br>


<h4>Remove files containing a string</h4>
```
rm ?*foo?*
ls -d '*foo*' | egrep -v '^foo|foo$' | xargs rm
```

<br>

---

<br>

<h4>Create folder and cd into it</h4>
```
mkdir foo && cd "$_"
```

<br>

---

<br>

<h4>Create Swap file</h4>
```
sudo mkdir -v /var/cache/swap
cd /var/cache/swap
sudo dd if=/dev/zero of=swapfile bs=1K count=8M
sudo chmod 600 swapfile
sudo mkswap swapfil
sudo mkswap swapfile
sudo swapon swapfile
top -bn1 | grep -i swap
echo "/var/cache/swap/swapfile none swap sw 0 0" | sudo tee -a /etc/fstab
```

<br>

---

<br>

<h4>Change permission in filder and files</h4>
```
Chmod chown
find . -type d -exec chmod 777 {} +
find . -type f -exec chmod 777 {} +
```

<br>

---

<br>

<h4>Mount/Unmount</h4>
```
cat /proc/partitions
mknod
mknod /dev/vdb b 252 16
fdisk /dev/vdb
mkfs.ext3 /dev/vdb
mkdir  /tmp/ciao
mount /dev/vdb /tmp/ciao
unmount /tmp/ciao
```

<br>

---

<br>

<h4>Compress/Uncompress  Files</h4>
Create a tar archive of a directory
```
tar -cvf tarball_name.tar  /path/to/directory
```

c - Used for creating a new .tar file  
v - Verbosely outputs the creation of the .tar file  
f - Defines the file name of the archive file  
  
Create a tar.gz archive file
```
tar -cvzf james.tar.gz  /home/james/
```

create a bz2 archiv (j option)
```
tar -cvjf james.tar.bz2  /home/james/
```

---

To uncompress or untar a .tar file , use the x option  
```
tar -xvf james.tar
```

To extract the file to a different directory, use the -C + path  
```
tar -xvf james.tar  -C /opt
```

Uncompressing a tar.gz file  
```
tar -xvf james.tar.gz
```
Sample output

---
List contents of a tar file  
```
tar -tvf james.tar
```

List contents of a tar.bz2
```
tar -tvf james.tar.bz2
```

Set Default folder for screenshots
```
gsettings set org.gnome.gnome-screenshot auto-save-directory "file:///home/username/Pictures/GUI/"
```

<br>

---

<br>

<h4>Download files from command line</h4>
```
curl -L -o "/dir1/dir2/miofile.txt" "https://turbolab.it/scarica/204"
wget -O "/dir1/dir2/miofile.txt" "https://turbolab.it/scarica/204"
```

<br>

---

<br>

<h4>Download files from command line and assign name</h4>
curl -o "miofile.txt" "https://turbolab.it/scarica/204"
wget -O "miofile.txt" "https://turbolab.it/scarica/204"

<br>

---

<br>

<h4>REGEX</h4>
[Regex checker](https://regex101.com/)  
[Regex examples](https://projects.lukehaas.me/regexhub/)  
[Regex cheatsheet](https://www.keycdn.com/support/regex-cheatsheet)  
  
Anchor Matches  
Anchors are special characters that specify where in the line a match must occur to be valid.  
```
grep "^GNU" GPL-3 // ^ Match initial part of line
grep "and$" GPL-3 // $ Match end of line
```
  
Matching Any Character  
```
grep "..cept" GPL-3 // .. 2 characters and then cept
```
  
Bracket Expressions  
```
grep "t[wo]o" GPL-3 //By placing a group of characters within brackets ("[" and "]"), 
we can specify that the character at that position can be any one character found within the bracket group.

grep "^[A-Z]" GPL-3 // find every line that begins with a capital letter
```

Repeat Patterns  
```
grep "([A-Za-z ]*)" GPL-3 // each line that contained an opening and closing parenthesis
```

Escaping Meta-Characters  
```
grep "^[A-Z].*\.$" GPL-3 // find any line that begins with a capital letter and ends with a period
```

Alternation  
```
grep -E "(GPL|General Public License)" GPL-3 // find either "GPL" or "General Public License" 
```

Quantifiers
```
grep -E "(copy)?right" GPL-3 // matches "copyright" and "right" by putting "copy" in an optional group
```

Match Repetition
```
grep -E "[AEIOUaeiou]{3}" GPL-3 // contain triple-vowels
grep -E "[[:alpha:]]{16,20}" GPL-3 // any words that have between 16 and 20 characters
```



```
let regex;

/* matching a specific string */
regex = /hello/; // looks for the string between the forward slashes (case-sensitive)... matches "hello", "hello123", "123hello123", "123hello"; doesn't match for "hell0", "Hello" 
regex = /hello/i; // looks for the string between the forward slashes (case-insensitive)... matches "hello", "HelLo", "123HelLO"
regex = /hello/g; // looks for multiple occurrences of string between the forward slashes...

/* wildcards */
regex = /h.llo/; // the "." matches any one character other than a new line character... matches "hello", "hallo" but not "h\nllo"
regex = /h.*llo/; // the "*" matches any character(s) zero or more times... matches "hello", "heeeeeello", "hllo", "hwarwareallo"

/* shorthand character classes */
regex = /\d/;  // matches any digit
regex = /\D/;  // matches any non-digit
regex = /\w/;  // matches any word character (a-z, A-Z, 0-9, _)
regex = /\W/;  // matches any non-word character
regex = /\s/;  // matches any white space character (\r (carriage return),\n (new line), \t (tab), \f (form feed))
regex = /\S/;  // matches any non-white space character

/* specific characters */
regex = /[aeiou]/; // matches any character in square brackets
regex = /[ck]atherine/; // matches catherine or katherine
regex = /[^aeiou]/; // matches anything except the characters in square brackets

/* character ranges */
regex = /[a-z]/; // matches all lowercase letters
regex = /[A-Z]/; // matches all uppercase letters
regex = /[e-l]/; // matches lowercase letters e to l (inclusive)
regex = /[F-P]/; // matches all uppercase letters F to P (inclusive)
regex = /[0-9]/; // matches all digits
regex = /[5-9]/; // matches any digit from 5 to 9 (inclusive)
regex = /[a-zA-Z]/; // matches all lowercase and uppercase letters
regex = /[^a-zA-Z]/; // matches non-letters

/* matching repetitions using quantifiers */
regex = /(hello){4}/; // matches "hellohellohellohello"
regex = /hello{3}/; // matches "hellooo" and "helloooo" but not "helloo"
regex = /\d{3}/; // matches 3 digits ("312", "122", "111", "12312321" but not "12")
regex = /\d{3,7}/; // matches digits that occur between 3 and 7 times (inclusive)
regex = /\d{3,}/; // matches digits that occur at least 3 times

/* matching repetitions using star and plus */
regex = /ab*c/; // matches zero or more repetitions of "b" (matches "abc", "abbbbc", "ac")
regex = /ab+c/; // matches one or more repetitions of "b" (matches "abc", "abbbbc", but not "ac")

/* matching beginning and end items */
regex = /^[A-Z]\w*/; // matches "H", "Hello", but not "hey"
regex = /\w*s$/; // matches "cats", "dogs", "avocados", but not "javascript"

/* matching word boundaries 

positions of word boundaries:
1. before the first character in string (if first character is a word character)
2. after the last character in the string, if the last character is a word character
3. between two characters in string, where one is a word character and the other isn't */
regex = /\bmeow\b/; // matches "hey meow lol", "hey:meow:lol", but not "heymeow lol"

/* groups */
regex = /it is (ice )?cold outside/; // matches "it is ice cold outside" and "it is cold outside"
regex = /it is (?:ice )?cold outside/; // same as above except it is a non-capturing group
regex = /do (cats) like taco \1/; // matches "do cats like taco cats"
regex = /do (cats) like (taco)\? do \2 \1 like you\?/; // matches "do cats like taco? do taco cats like you?"

//branch reset group (available in Perl, PHP, R, Delphi... commented out because this is a js file)
// regex = /(?|(cat)|(dog))\1/; // matches "catcat" and "dogdog"

/* alternative matching */
regex = /i like (tacos|boba|guacamole)\./; // matches "i like tacos.", "i like boba.", and "i like guacamole."

/* forward reference (available in Perl, PHP, Java, Ruby, etc... commented out because this is a js file) */
// regex = /(\2train|(choo))+/; // matches "choo", "choochoo", "chootrain", choochootrain", but not "train"

/* lookaheads */
regex = /z(?=a)/; // positive lookahead... matches the "z" before the "a" in pizza" but not the first "z"
regex = /z(?!a)/; // negative lookahead... matches the first "z" but not the "z" before the "a"

/* lookbehinds */
regex = /(?<=[aeiou])\w/; // positive lookbehind... matches any word character that is preceded by a vowel
regex = /(?<![aeiou])\w/; // negative lookbehind... matches any word character that is not preceded by a vowel

/* functions I find useful */
regex.test("hello"); // returns true if found a match, false otherwise
regex.exec("hello"); // returns result array, null otherwise
"football".replace(/foot/,"basket"); // replaces matches with second argument
```

<br>

---

<br>

## NODE / NPM  

<br>

---

<br>

<h4>Check Version</h4>
```
which node
which npm
node --version
npm --version
```

<br>

---

<br>

<h4>Update to latest version</h4>
```
sudo npm cache clean -f
sudo npm install -g n
sudo n stable
```

<br>

---

<br>

<h4>Global install packages</h4>
```
npm install uglify-js --global
```

<br>

---

<br>

<h4>List global packages</h4>
```
npm list --global
npm list -g --depth=0
```

<br>

---

<br>

<h4>Initialize project</h4>
```
npm init
```

<br>

---

<br>

<h4>Local install packages devDependencies</h4>
```
npm install should --save-dev
```

<br>

---

<br>

<h4>Local install packages dependencies</h4>
```
npm install should --save
```

<br>

---

<br>

<h4>Uninstall packages</h4>
```
npm uninstall underscore
```

<br>

---

<br>

<h4>Install specific version</h4>
```
npm install underscore@1.8.2
```

<br>

---

<br>

<h4>Check outdated packages</h4>
```
npm outdated
```

<br>

---

<br>

<h4>Update packages</h4>
```
npm update underscore
```

<br>

---

<br>

<h4>Quick Project Setup - React, Webpack, Babel, ESLint</h4>
 
<h4>Dependencies</h4>
```
npm install --save react react-dom
```

<h4>Dev Dependencies</h4>
```
npm install --save-dev babel-{core,loader} babel-preset-es2015 babel-preset-react babel-eslint css-loader node-sass sass-loader style-loader file-loader webpack webpack-dev-server eslint eslint-plugin-import eslint-plugin-react eslint-watch
```

<h4>NPM Scripts (package.json)</h4>
```
"scripts": {
  "start": "webpack-dev-server --progress --hot --inline",
  "build": "webpack",
  "lint": "esw webpack.config.js src",
  "lint:watch": "npm run lint -- --watch",
  "fix": "./node_modules/.bin/eslint src --fix"
},
```

<h4>NVM: manage different versions of Node:</h4>
```
$ curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.33.0/install.sh | bash
```

```
$ export NVM_DIR=”$HOME/.nvm”
$ [ -s “$NVM_DIR/nvm.sh” ] && \. “$NVM_DIR/nvm.sh”
$ [ -s "$NVM_DIR/bash_completion" ] && \.   "$NVM_DIR/bash_completion"
```

<br>

---

<br>

<h4>Install a new version</h4>
```
nvm install 8.9.4
```

<br>

---

<br>

<h4>Show available versions of node</h4>
```
nvm ls
```

<br>

---

<br>

<h4>Use a particular version</h4>
```
nvm use 10.15.3
```

<br>

---

<br>

<h4>Babel (.babelrc)</h4>
```
{
  "presets": [
    "es2015",
    "react"
  ]
}
```

<br>

---

<br>

<h4>Move a module from devDependencies to dependencies</h4>
```
npm install <module_name> --save-prod
```
or  
```
yarn remove <module_name> --dev&yarn add <module_name> 
```

<br>

---

<br>

<h4>Move a module from dependencies to devDependencies</h4>
```
npm install <module_name> --save-dev
```
or  
```
yarn remove <module_name>&yarn add <module_name> --dev
```

<br>

---

<br>

## WEBPACK

Webpack is a static module bundler for modern JavaScript applications.  
It internally builds a dependency graph which maps every module your project needs and generates one or more bundles.  
Any time one file depends on another, webpack treats this as a dependency.  
Core Concepts:  
  
- Entry  
An entry point indicates which module webpack should use to begin building out its internal dependency graph.  
```js
module.exports = {
  entry: './path/to/my/entry/file.js'
};
```
  
- Output  
The output property tells webpack where to emit the bundles it creates and how to name these files.  
```js
module.exports = {
  output: {
    filename: 'bundle.js',
  }
};
```

- Loaders  
Loaders allow webpack to process other types of files and convert them into modules.  
For example, you can use loaders to tell webpack to load a CSS file or to convert TypeScript to JavaScript. To do this, you would start by installing the loaders you need:  
```
npm install --save-dev css-loader
npm install --save-dev ts-loader
```

```js
module.exports = {
  module: {
    rules: [
      { test: /\.css$/, use: 'css-loader' },
      { test: /\.ts$/, use: 'ts-loader' }
    ]
  }
};
```

- Plugins  
Plugins can be leveraged to perform a wider range of tasks like bundle optimization  
Since plugins can take arguments/options, you must pass a new instance to the plugins property in your webpack configuration.  

```js
const HtmlWebpackPlugin = require('html-webpack-plugin'); //installed via npm
const webpack = require('webpack'); //to access built-in plugins
const path = require('path');

module.exports = {
  entry: './path/to/my/entry/file.js',
  output: {
    filename: 'my-first-webpack.bundle.js',
    path: path.resolve(__dirname, 'dist')
  },
  module: {
    rules: [
      {
        test: /\.(js|jsx)$/,
        use: 'babel-loader'
      }
    ]
  },
  plugins: [
    new webpack.ProgressPlugin(),
    new HtmlWebpackPlugin({template: './src/index.html'})
  ]
};
```

- Mode  
By setting the mode parameter to either development, production or none, you can enable webpack's built-in optimizations that correspond to each environment.
- Browser Compatibility  
Webpack supports all browsers that are ES5-compliant (IE8 and below are not supported).

---

<h4>Webpack installation</h4>
```
npm install --save-dev webpack
```

Webpack Client
```
npm install --save-dev webpack-cli
```

Minimal webpack configuration  
file e.g. webpack.config.js  
```
var path = require('path');

module.exports = {
  mode: 'development',
  entry: './foo.js',
  output: {
    path: path.resolve(__dirname, 'dist'),
    filename: 'foo.bundle.js'
  }
};
```
in package.json  
```
 "scripts": {
      "build": "webpack"
    },
```

---

<h4>Webpack Performance codesplitting react-loadable</h4>
```
npm install --save react-loadable
```

```
import Loadable from 'react-loadable';
import Loading from '../../layout/Loading';
const ComponentName = Loadable({ loader: () => import(/* webpackChunkName: "ComponentName" */'./subcomponents/ComponentName'), loading: Loading });
```

in webpack.config.js
```
  output: {
    path: path.join(__dirname, 'app/static/bin'),
    filename: 'bundle.js',
    publicPath: '/static/bin/',
    chunkFilename: '[name].bundle.js',
  },
```

<h4>Performance improvements</h4>
```
Webpack Plugin: UglifyWebpackPlugin minify js files
(license MIT) uglifyjs-webpack-plugin

Webpack Plugin: MomentLocalesPlugin remove unused locales from Moment
(license MIT) moment-locales-webpack-plugin

Webpack Plugin: BundleAnalyzerPlugin analyze build files (use http://127.0.0.1:8888 after running npm run-script build)
(license MIT): Webpack Bundle Analyzer

Babel Plugin: transform-imports import only needed modules
(license ISC) babel-plugin-transform-imports

Babel Plugin: transform-react-remove-prop-types Remove React propTypes from the production build, as they are only used in development.
(license MIT) babel-plugin-transform-react-remove-prop-types
```

webpack treeshaking
```
npm run-script build -- --display-used-exports
```

.babelrc transform imports
npm install --save-dev babel-plugin-transform-imports  
in .babelrc

```
{
    "plugins": [
        ["transform-imports", {
            "react-bootstrap": {
                "transform": "react-bootstrap/lib/${member}",
                "preventFullImport": true
            },
            "lodash": {
                "transform": "lodash/${member}",
                "preventFullImport": true
            }
        }]
    ]
}
```

.eslintrc configuration
```
module.exports = {
    "parser": "babel-eslint",
    "extends": "airbnb",
    "env": {
        "browser": true
    },
    "rules": {
      "class-methods-use-this": "off",
      "react/sort-comp": "off"
    }
};
```

Webpack (webpack.config.js)
```
const path = require('path');

module.exports = {
	target: 'web',

	// Entry file where webpack starts the bundling process
	entry: path.resolve(__dirname, 'src/index.js'),

	// Location where bundled code will be saved
	output: {

		// Target directory for all output files
		path: path.resolve(__dirname, './dist'),

		// Name of each Output bundle file
		filename: "bundle.js",
	},

	// Webpack development server (config)
	devServer: {
		port: 9000,

		// Directory to serve content from
		contentBase: path.resolve(__dirname, './src'),

		// Automatically open browser when local server boots up
		open: true
	},

	// Source Map setting
	devtool: "inline-source-map",

	// Modules & Loaders
  module: {
    rules: [
      {
        test: /\.js$/,
        loader: 'babel-loader',
        exclude: /node_modules/
      },
      {
        test: /\.(jpe?g|png|gif)$/i,
        loader: 'file-loader',
        exclude: /node_modules/
      },
      {
        test: /(\.css|\.scss|\.sass)$/,
        loaders: [
          'style-loader',
          'css-loader',
          'sass-loader'
        ]
      }
    ]
  }
};
```

ESLint (.eslintrc.json)
```
{
  "root": true,
  "extends": [
    "eslint:recommended",
    "plugin:import/errors",
    "plugin:import/warnings"
  ],
  "plugins": [
    "react"
  ],
  "parser": "babel-eslint",
  "parserOptions": {
    "ecmaVersion": 7,
    "sourceType": "module",
    "ecmaFeatures": {
      "jsx": true
    }
  },
  "env": {
    "es6": true,
    "browser": true,
    "node": true,
    "mocha": true
  },
  "rules": {
    "quotes": 0,
    "no-console": 1,
    "no-debugger": 1,
    "no-var": 1,
    "semi": [1, "always"],
    "no-trailing-spaces": 1,
    "eol-last": 0,
    "no-unused-vars": 1,
    "no-underscore-dangle": 0,
    "no-alert": 0,
    "no-lone-blocks": 0,
    "no-multi-spaces": 1,
    "jsx-quotes": 1,
    "react/display-name": [ 1, {"ignoreTranspilerName": false }],
    "react/forbid-prop-types": [1, {"forbid": ["any"]}],
    "react/jsx-boolean-value": 1,
    "react/jsx-closing-bracket-location": 1,
    "react/jsx-curly-spacing": 1,
  }
}
```
---
Webpack setup2
-y takes the default
```
npm init -y
```
From root folder:
```
mkdir dist
cd dist
touch index.html
```
in dist/index.html
```
<!DOCTYPE html>
<html>
  <head>
    <title>The Minimal React Webpack Babel Setup</title>
  </head>
  <body>
    <div id="app"></div>
    <script src="./bundle.js"></script>
  </body>
</html>
```
Install Webpack from root folder
```
npm install --save-dev webpack webpack-dev-server webpack-cli
```
Folder Structure
```
- dist
-- index.html
- node_modules
- package.json
```
package.json
```
"scripts": {
  "start": "webpack-dev-server --config ./webpack.config.js --mode development",
  ...
},
```
Create webpack configuration file
```
touch webpack.config.js
```
webpack config content
```
module.exports = {
  entry: './src/index.js',
  output: {
    path: __dirname + '/dist',
    publicPath: '/',
    filename: 'bundle.js'
  },
  devServer: {
    contentBase: './dist'
  }
};
```
Start Webpack dev server
```
npm start
```
---

<h4>Webpack enable sourcemap</h4>
in webpack.config.js
```js
module.exports = {
  entry: path.join(__dirname, "src", "index.js"),
  devtool: 'source-map',
  output:...........
```

---

## BABEL

Babel transpiles back to vanilla JavaScript so that every browser can interpret it. 
```
npm install --save-dev @babel/core @babel/preset-env
```
hook it to webpack
```
npm install --save-dev babel-loader
```
JSX to javasript
```
npm install --save-dev @babel/preset-react
```
package.json
```
"keywords": [],
"author": "",
"license": "ISC",
"babel": {
  "presets": [
    "@babel/preset-env",
    "@babel/preset-react"
  ]
```
webpack.config.json
```
module.exports = {
  entry: './src/index.js',
  module: {
    rules: [
      {
        test: /\.(js|jsx)$/,
        exclude: /node_modules/,
        use: ['babel-loader']
      }
    ]
  },
  resolve: {
    extensions: ['*', '.js', '.jsx']
  },
  output: {
    path: __dirname + '/dist',
    publicPath: '/',
    filename: 'bundle.js'
  },
  devServer: {
    contentBase: './dist'
  }
};
```

Install packages for react
```
npm install --save react react-dom
```
src/index.js
```
import React from 'react';
import ReactDOM from 'react-dom';

const title = 'My Minimal React Webpack Babel Setup';

ReactDOM.render(
  <div>{title}</div>,
  document.getElementById('app')
);
```

Hot Module Replacement in React  
apply changes to the browser
```
npm install --save-dev react-hot-loader
```
webpack.config.js
```
const webpack = require('webpack');

module.exports = {
  entry: './src/index.js',
  module: {
    rules: [
      {
        test: /\.(js|jsx)$/,
        exclude: /node_modules/,
        use: ['babel-loader']
      }
    ]
  },
  resolve: {
    extensions: ['*', '.js', '.jsx']
  },
  output: {
    path: __dirname + '/dist',
    publicPath: '/',
    filename: 'bundle.js'
  },
  plugins: [
    new webpack.HotModuleReplacementPlugin()
  ],
  devServer: {
    contentBase: './dist',
    hot: true
  }
};
```

in src/index.js add at the end
```
module.hot.accept();
```
```
npm start
```

---

## CURL

<h4>SET SITE</h4>
```
SITE=localhost:8096
```
<h4>TOKEN AUTHENTICATION</h4>
```
TOKEN=`curl -v $SITE/api/v1/Sessions -d'{"UserName":"Admin", "Password":"pass"}' 2>&1|sed -n 's/.*\(X-Auth-Token:\) /\1/p'` && echo $TOKEN
```
<h4>BASIC AUTHENTICATION</h4>
```
curl -v -uAdmin:pass $SITE/api/v1/
```
<h4>GET USERS</h4>
```
curl -v -H$TOKEN $SITE/api/v1/Accounts/
```
<h4>POST</h4>
```
curl -v -H$TOKEN $SITE/api/v1/Accounts/ -d'{"UserName":"abcde", "Password":"edcba", "RoleId":"Operator"}' |python -mjson.tool
```
<h4>PATCH</h4>
```
curl -v -X PATCH -H$TOKEN $SITE/api/v1/Accounts/abcde -d'{"Password":"zyxwv"}' |python -mjson.tool
```
<h4>DELETE</h4>
```
curl -v -X DELETE -H$TOKEN $SITE/api/v1/Accounts/abcde
```


--- 


## DOCKER  

Docker is a platform to develop, deploy, and run applications with containers.  
A container is launched by running an image.  
An image is an executable package that includes everything needed to run an application--the code, a runtime, libraries, environment variables, and configuration files.  

<h4>Example 1</h4>

1. create an application
2. create a Dockerfile
3. build an image
4. create a container
5. using a volume

<h4>1. create an application</h4>
```
npm init -y
npm install express —-save
```

app.js
```js
// app.js
const express = require('express')

const app = express()

const port = 3000

app.get('/', (req, res) => res.send('Hello World!'))

app.listen(port, () => console.log(`Example app listening on port ${port}!`))
```

run it
```
node app.js
```

<h4>2. create a Dockerfile</h4>

```
FROM node:latest

WORKDIR /app

COPY . .

RUN npm install

EXPOSE 3000

ENTRYPOINT ["node", "app.js"]
```

<h4>3. build an image</h4>

```
docker build -t mz2kh/node:latest .
```

Show images
```
docker images
```

<h4>4. create a container</h4>

Create a container with docker run

```
docker run mz2kh/node
or
docker run -p 8000:3000 chrisnoring/node
```

Environment variable
```
ENV PORT=3000
use in Dockerfile: EXPOSE $PORT
use in Node.js process.env.PORT
```

List containers
```
docker ps
```

Stop containers
```
docker stop containerID
```

Access contaienr shell interactively
```
docker exec -it containerID bash
```

Remove container
```
docker rm containerID
```

<h4>5. using a Volume</h4>
We want to be able to change or create files in our container so that
when we pull it down and start it up again our changes will still be there.

create a volume
```
docker volume create [name of volume]
```

volumes list
```
docker volume ls
```

remove all not used volumes
```
docker volume prune
```

remove a single volume
```
docker volume rm [name of volume]
```

get more information about a volume
```
docker inspect [name of volume]
```

<h4>Mounting a volume</h4>

Syntax options:
```
--volume (-v [name of volume]:[directory in the container])
or 
--mount (--mount source=[name of volume], target=[directory in container])
```

Usage in conjunction with run container
```
docker run -d -p 8000:3000 --name my-container --volume my-volume:/logs mz2kh/node
```

Locate our volume inside of our container, and navigate to logs/ directory
```
docker exec -it my-container bash
```

Run container with subdirectory
```
docker run -d -p 8000:3000 --name my-container --volume $(pwd)/logs:/logs mz2kh/node
```

access container and check folder cd ../logs/
```
docker exec -it my-container bash
```

tear down the container
```
docker kill my-container && docker rm my-container
```

Make the entire project directory as a volume
```
npm install --save-dev nodemon
docker run -d -p 8000:3000 --name my-container --volume $(pwd):/app mz2kh/node
```
in package.json add
```
"scripts": {
  "start": "nodemon app.js",
  "log": "echo \"Logging something to screen\""
}
```
in Dockerfile change entrypoint to:
```
ENTRYPOINT ["npm", "start"]
```
rebuild the image
```
docker build -t mz2kh/node .
```
bring up our container
```
docker run -d -p 8000:3000 --name my-container --volume $(PWD):/app mz2kh/node
```


<h4>Example 2</h4>
Develop a new project which involves both a Node backend and a React front-end in Docker containers.
- Run both the Node and the React app in its own Docker container.
- Communicate between the two apps running in containers.
- Every edit in the local IDE will automatically be reflected in the apps running in containers.

1. Create a repository with a backend and frontend folder
2. Add outside both folders a docker-compose.yml file to build and spin up the two containers
3. Add a .env file providing default values of environment variables for both apps.
4. Add a Dockerfile in the client folder and also one in the server folder

For Client
```
# base image
FROM node:latest

# set working directory
RUN mkdir -p /usr/src/appclient
WORKDIR /usr/src/appclient

# install dependencies
COPY package.json /usr/src/appclient
COPY package-lock.json /usr/src/appclient

RUN npm install

COPY . /usr/src/appclient

# start app
CMD ["npm", "start"]
```

For Server
```
# base image
FROM node:8.7.0-alpine

# set working directory
RUN mkdir -p /usr/src/appserver
WORKDIR /usr/src/appserver

# install dependencies
COPY package.json /usr/src/appserver
COPY package-lock.json /usr/src/appserver

RUN npm install

COPY . /usr/src/appserver

# start app
CMD ["npm", "run", "dev"]
```

a. FROM node:8.7.0-alpine Tell Docker we want to use Node v8.7.0 installed in a alpine Linux image.  
b. RUN mkdir -p /app/directory/path Create a directory in the container to hold the app.  
c. WORKDIR /app/directory/path Go into the app folder by making it the working directory  
d. COPY package.json and COPY package-lock.json Copy the local package.json and package-lock.json files into the container  
e. RUN npm install install the node modules that the project needs  
f. COPY . /app/directory/path Copy local code into the container  
g. CMD ["npm", "start"] Now our app lives in the container, we can run the command npm start.  
  
e. The Dockerfile in the server folder is nearly the same, except that in the last line the command to run is npm run dev , which is an npm script  defined in the package.json file that starts the Node app using nodemon instead of node to trigger recompiling the app server every time I edit something in the local server source code.  


<h4>Create the docker-compose.yml file</h4> 
This will make the two containers communicative.

```
version: '3.5'

services:
################################
# Setup node container
################################
  server:
    build: ./server
    espose: 
      - ${APP_SERVER_PORT}
    environment:
      API_HOST: ${API_HOST}
      APP_SERVER_PORT: ${APP_SERVER_PORT}
    ports:
      - ${APP_SERVER_PORT}:${APP_SERVER_PORT}
    volumes:
      - ./server/src:/srv/appserver/src
    command: npm run dev
################################
# Setup client container
################################
  client:
    build: ./client
    environment:
      REACT_APP_PORT: ${REACT_APP_PORT}
    espose: 
      - ${REACT_APP_PORT}
    ports:
      - ${REACT_APP_PORT}:${REACT_APP_PORT}
    volumes:
      - ./client/src:/srv/appclient/src
    links:
      - server
    command: npm run start
```

Variables are defined in an external files .env:
```
API_HOST="http://localhost:3000"
APP_SERVER_PORT=8000
REACT_APP_PORT=4000
```

a. ports: Then we map container port to a port on the host machine so that we can access the running containers from the local environment  
b. volumes: Mounting volumes enables us to map local source code to the corresponding code in the container,  
   so that every time we edit these code files in our local IDE the changes will be instantly reflected in the container.  
c. command: The command to run after the container is up. What’s specified here will override the CMD part in the Dockerfile.  

<!-- 
https://medium.com/@xiaolishen/develop-in-docker-a-node-backend-and-a-react-front-end-talking-to-each-other-5c522156f634
https://dev.to/azure/docker---from-the-beginning-part-i-28c6
-->

---

## CROSS BROWSERS

Common issues: 

- Avoid Internet Explorer to fall back to it’s own Quirksmode:
```html
<!DOCTYPE html>
```

- Add CSS Reset as: https://github.com/necolas/normalize.css/blob/master/normalize.css

- Vendor specific style
```
-ms for Microsoft (Internet Explorer)
-moz for Mozilla Foundation (Firefox)
-o for Opera Software
-webkit  for Safari and Chrome
```

```
.test{
 -moz-opacity: 0.6;
 -ms-opacity: 0.6;
 -webkit-opacity: 0.6;
 opacity: 0.6;
}
```

- Use cross-browser friendly libraries and frameworks: Bootstrap, JQuery...


---


## DEVOPS
DevOps is a combination of practices, and tools that increases an organization’s ability to deliver applications and services at high velocity to better serve their customers and compete more effectively in the market.  
  
These practices are used to automate processes that historically have been manual and slow. They use a technology stack and tooling which help them operate and evolve applications quickly and reliably.  
  
Benefits of DevOps  
For example, microservices and continuous delivery let teams take ownership of services and then release updates to them quicker.  
Increase the frequency and pace of releases so you can innovate and improve your product faster.  
Continuous integration and continuous delivery are practices that automate the software release process, from build to deploy.  

Reliability  
Ensure the quality of application updates and infrastructure.  
Test that each change is functional and safe.  
Monitoring and logging practices help you stay informed of performance in real-time.  
  
Scale  
Operate and manage your infrastructure and development processes at scale. Automation and consistency.  
  
Software and the Internet have transformed the world and its industries, from shopping to entertainment to banking.  
Software no longer merely supports a business; rather it becomes an integral component of every part of a business.  

There are a few key practices that help organizations innovate faster through automating and streamlining the software development and infrastructure management processes. Most of these practices are accomplished with proper tooling.  
  
One fundamental practice is to perform very frequent but small updates. This is how organizations innovate faster for their customers. These updates are usually more incremental in nature than the occasional updates performed under traditional release practices.  
  
Organizations might also use a microservices architecture to make their applications more flexible and enable quicker innovation.  
The microservices architecture decouples large, complex systems into simple, independent projects.  
Applications are broken into many individual components (services).  
  
However, the combination of microservices and increased release frequency leads to significantly more deployments which can present operational challenges.  
Thus, DevOps practices like continuous integration and continuous delivery solve these issues and let organizations deliver rapidly in a safe and reliable manner.   Infrastructure automation practices, like infrastructure as code and configuration management, help to keep computing resources elastic and responsive to frequent changes.  
In addition, the use of monitoring and logging helps engineers track the performance of applications and infrastructure so they can react quickly to problems.  
  
The following are DevOps best practices:  
  
Continuous Integration  
Continuous Delivery  
Microservices  
Infrastructure as Code  
Monitoring and Logging  
Communication and Collaboration  
Below you can learn more about each particular practice.  
Continuous Integration  

---

## VSCODE
<h4>Debug code through Chrome Debugger extension</h4>
Launch VS Code Quick Open (Ctrl+P), paste the following command, and press enter.  
```
ext install msjsdiag.debugger-for-chrome
```

<h4>Create a launch file for the Visual Studio Code Debugger.</h4>
Click gear icon on debug section (Ctr+Shift+D).  
Select option "Chrome"  
Insert a configuration file  
Insert url, root, name  
```
{
     "version": "0.2.0",
    "configurations": [
        {
            "type": "chrome",
            "request": "launch",
            "name": "Launch Chrome against localhost",
            "url": "http://127.0.0.1:8887",
            "webRoot": "${workspaceFolder}"
        }
    ]
}
```
Add breakpoints in VS Code, by click on the left of row number  
Press F5 to start debugging  
A new chrome window will open  

In VS Code
Open debug panel ctlr+shift+D
Press F10 for step over  
Press F11 for step into  
Press shift + F11 for step out  
Press F6 for pause  

---

<h4>Create Snippet</h4>
```
ctrl+shift+p
Preferences: Configure User Snippets
Select Javascript
```

'''
{
  "Console Log": {
    "prefix": "xcl",
    "body": 
      [,
      "renderA() {}",
      "renderB() {}",
      ],
    "description": "render() {}"
  }
}
'''
type "xcl" to use it
[Snippet Generator](https://snippet-generator.app/)

---

<br>

---

<br>

## OTHER TOOLS

<h4>Jenkins</h4>
Jenkins is a cross-platform, continuous integration and continuous delivery application.  
Use Jenkins to build and test your software projects continuously.  
It provides powerful ways to define your build pipelines and integrating with testing and deployment technologies.  

build > test > deploy it is the most common pattern

Jenkins is a continuous integration server.  
Integration tests take all the code and other components of your application and integrate it together, then test it to ensure it's working properly.  
Jenkins can watch repos for version control software like Git or Subversion.  
When there's a new commit, Jenkins will check it out automatically.  
It will run your tests, and report the result.  
It can even be configured to automatically deploy your software to production if all the tests pass.

A Jenkins pipeline delivers your software to a testing, staging, or production environment.  
When creating a pipeline, you specify the steps Jenkins needs to follow.  
Anytime a build is triggered, Jenkins will follow those steps to deliver your code where it needs to go.  

Pipeline scripts use a domain-specific language based on the Groovy programming language.  
They start with the pipeline keyword, followed by a block in curly braces ({}).  
The components of the pipeline are nested within that block.  
We'll look at the agent and stages declarations later in the course; 

```json
pipeline {
    agent any 
    stages {
        stage('My Stage') {
            steps {
                sh 'pwd'
                // If you're on Windows, use this line instead:
                // bat 'cd'
                sh 'whoami'
                // If you're on Windows, use this line instead:
                // bat 'whoami'
                sh 'mkdir newfolder'
                // If you're on Windows, use this line instead:
                // bat 'mkdir newfolder'
                sh 'ls'
                // If you're on Windows, use this line instead:
                // bat 'dir'
            }
        }
    }
}
```

Save your changes, return to the pipeline screen, and click "Build Now" in the left-hand menu.  
A new build will appear in the "Build History" area;  
click it and open its "Console Output".  
You'll see something like the following:

```json
Started by user Jay McGavren
Running in Durability level: MAX_SURVIVABILITY
[Pipeline] Start of Pipeline
[Pipeline] node
Running on Jenkins in /Users/jay/.jenkins/workspace/Shell Pipeline
[Pipeline] {
[Pipeline] stage
[Pipeline] { (My Stage)
[Pipeline] sh
+ pwd
/Users/jay/.jenkins/workspace/Shell Pipeline
[Pipeline] sh
+ whoami
jay
[Pipeline] sh
+ mkdir newfolder
[Pipeline] sh
+ ls
newfolder
[Pipeline] }
[Pipeline] // stage
[Pipeline] }
[Pipeline] // node
[Pipeline] End of Pipeline
Finished: SUCCESS
```

With Docker, your compiler, database, and everything else your app needs can be installed in a docker image.  
Then, Jenkins can launch a Docker container based on that image, and run all your sh or bat steps within the container.  You can be certain that all of your app's dependencies are installed correctly, and there's no need to clutter the Jenkins server.


## BASH

example
```bash
#!/bin/bash
who='You!'

echo write name:

read whoami

echo Hello, World!, $who! $whoami

echo write number

read age

if [ "$age" -gt 20 ]
then
    echo You can drink.
else
    echo You are too young to drink.
fi


FILES=/home/matteo/*

for file in $FILES
do
    echo $(basename $file)
done


read -r -p 'Commit message: ' desc  # prompt user for commit message
git add .                           # track all files
git add -u                          # track deletes
git commit -m "$desc"               # commit with message
git push origin master              # push to origin
```





## LINKS

React  
[Awesome-react](https://github.com/enaqx/awesome-react)  
[React Learning Roadmap](https://raw.githubusercontent.com/adam-golab/react-developer-roadmap/master/roadmap.png)  
[FreeCodeCamp: React Cocepts](https://medium.freecodecamp.org/these-are-the-concepts-you-should-know-in-react-js-after-you-learn-the-basics-ee1d2f4b8030)  
[Creativebloq: React Tips](https://www.creativebloq.com/news/5-expert-reactjs-tips-that-you-need-to-know-today)  
[React Various articles](https://react.christmas/)  
[Flavio Copes](https://flaviocopes.com)  
[Articles about frontend](https://alligator.io/)  
[Frontend Articles](https://www.robinwieruch.de/)  
[Frontend Articles](https://www.valentinog.com)  
[Hooks collection](https://nikgraf.github.io/react-hooks/)  
[30 seconds react](https://github.com/30-seconds/30-seconds-of-react#input)  
  
CSS Links  
[CSSreference.io](https://cssreference.io)  
[Jen Simmons CSS Lab](https://labs.jensimmons.com/)  
[BEM Block Element Modifier](https://www.toptal.com/css/introduction-to-bem-methodology)  
[CSS Animation](http://animista.net)  
[CSS grids](https://learncssgrid.com/)  
[Grids by example](https://gridbyexample.com)  
[Grid CSS Garden](http://cssgridgarden.com)  
[Grid CSS Tricks](https://css-tricks.com/snippets/css/complete-guide-grid/)  
[Flexbox CSS Tricks](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)  
[Flexbox Grid](http://flexboxgrid.com/)  

GIT  
[GIT commands](https://git-scm.com/docs)  

Linux  
[Linux commands](http://landoflinux.com/linux_basic_fundamentals.html)  

Docker
[Docker](https://dev.to/azure/docker---from-the-beginning-part-i-28c6)









































<!--
***********************************************************************************************************************
* DOCKER
***********************************************************************************************************************
Dockerize a React app.  

- Set up a development environment with code hot-reloading
- Configuring a production-ready image

<h4>Install create-react-app</h4>
```
npm install -g create-react-app@1.5.2
```

<h4>Create a new app</h4>
```
create-react-app sample-app
cd sample-app
```

<h4>Add Dockerfile to project root</h4>
Dockerfile defines what goes on in the environment inside your container.  
```
# base image
FROM node:9.6.1

# set working directory
RUN mkdir /usr/src/app
WORKDIR /usr/src/app

# add `/usr/src/app/node_modules/.bin` to $PATH
ENV PATH /usr/src/app/node_modules/.bin:$PATH

# install and cache app dependencies
COPY package.json /usr/src/app/package.json
RUN npm install --silent
RUN npm install react-scripts@1.1.1 -g --silent

# start app
CMD ["npm", "start"]
```

<h4>Add a .dockerignore:</h4>
```
node_modules
```

<h4>Build and tag the Docker image</h4>
```
docker build -t sample-app .
```

<h4>Spin up the container</h4>
```
sudo docker run -it -v ${PWD}:/usr/src/app -v /usr/src/app/node_modules -p 3000:3000 --rm sample-app
```

<h4>Check the app</h4>
Open your browser to: 
```
http://localhost:3000/
```

<h4>Docker compose</h4>
add docker-compose.yml
```
version: '3.5'

services:

  sample-app:
    container_name: sample-app
    build:
      context: .
      dockerfile: Dockerfile
    volumes:
      - '.:/usr/src/app'
      - '/usr/src/app/node_modules'
    ports:
      - '3000:3000'
    environment:
      - NODE_ENV=development
```

<h4>Build image and fire container</h4>
```
docker-compose up -d --build
```

<h4>Stop container</h4>
```
docker-compose stop
```

<h4>Docker example</h4>
Build an image, run container, publish image:
```
docker build -t friendlyhello .  # Create image using this directory's Dockerfile
docker run -p 4000:80 friendlyhello  # Run "friendlyhello" mapping port 4000 to 80
docker run -d -p 4000:80 friendlyhello         # Same thing, but in detached mode
docker container ls                                # List all running containers
docker container ls -a             # List all containers, even those not running
docker container stop <hash>           # Gracefully stop the specified container
docker container kill <hash>         # Force shutdown of the specified container
docker container rm <hash>        # Remove specified container from this machine
docker container rm $(docker container ls -a -q)         # Remove all containers
docker image ls -a                             # List all images on this machine
docker image rm <image id>            # Remove specified image from this machine
docker image rm $(docker image ls -a -q)   # Remove all images from this machine
docker login             # Log in this CLI session using your Docker credentials
docker tag <image> username/repository:tag  # Tag <image> for upload to registry
docker push username/repository:tag            # Upload tagged image to registry
docker run username/repository:tag                   # Run image from a registry
```

<h4>Docker Compose</h4>
Compose is a tool for defining and running multi-container Docker applications.  
With Compose, you use a YAML file to configure your application’s services.  

<h4>Services</h4>

In a distributed application, different pieces of the app are called “services”.  
To define, run, and scale services:  
1. Pull the image from the registry.
2. Run 5 instances of that image as a service called web.
3. Immediately restart containers if one fails.
4. Map port 4000 on the host to web’s port 80.
5. Instruct web’s containers to share port 80 via a load-balanced network called webnet.  

docker-compose.yml  
```yml
version: "3"
services:
  web:
    # replace username/repo:tag with your name and image details
    image: username/repo:tag
    deploy:
      replicas: 5
      resources:
        limits:
          cpus: "0.1"
          memory: 50M
      restart_policy:
        condition: on-failure
    ports:
      - "4000:80"
    networks:
      - webnet
networks:
  webnet:
```

Initialize containers service
```
docker swarm init
```

Run it
```
docker stack deploy -c docker-compose.yml getstartedlab
```

The single service stack is running 5 container instances of our deployed image on one host. 

<h4>Services cheatsheet</h4>
```
docker stack ls                                            # List stacks or apps
docker stack deploy -c <composefile> <appname>  # Run the specified Compose file
docker service ls                 # List running services associated with an app
docker service ps <service>                  # List tasks associated with an app
docker inspect <task or container>                   # Inspect task or container
docker container ls -q                                      # List container IDs
docker stack rm <appname>                             # Tear down an application
docker swarm leave --force      # Take down a single node swarm from the manager
```
-->












---

<!--
https://mherman.org/blog/dockerizing-a-react-app/
https://testdriven.io/courses/microservices-with-docker-flask-and-react/
-->

<!--
<h4>Docker terminology</h4>
Images: Executable to run containers.  
Containers: Running instance of a Docker image.  

Docker Daemon: background service to manage building, running and distributing containers.  
Docker Client: The command line tool that allows the user to interact with the daemon.  
Docker Hub: A registry of Docker images.  

---

<h4>Images Type</h4>
Base images: are images that have no parent image, usually images with an OS like ubuntu, busybox or debian.  
Child images: are images that build on base images and add additional functionality.  
Official images: are images that are officially maintained and supported by the folks at Docker
User images: images created and shared by users.

---

<h4>Install latest Docker</h4>
```
sudo apt-get install apt-transport-https ca-certificates curl software-properties-common
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add –
sudo add-apt-repository deb [arch=amd64] https://download.docker.com/linux/ubuntu  $(lsb_release -cs)  stable
sudo apt-get update
apt-cache madison docker-ce
docker-ce | 17.03.0~ce-0~ubuntu-xenial | https://download.docker.com/linux/ubuntu xenial/stable amd64 Packages
sudo apt-get install docker-ce=<VERSION>
```

or

```
 sudo apt-get update
 sudo apt-get remove docker docker-engine docker.io
 sudo apt install docker.io
 sudo systemctl start docker
 docker --version
```

<h4>Test your Docker installation by running the following</h4>
```
docker run hello-world
```
  
<h4>The pull command fetches image from the Docker registry and saves it to system.</h4>  
```
docker pull busybox
```

<h4>Docker Hub</h4>  
[Docker Images hub](https://hub.docker.com/search/?q=&type=image)  

<h4>List of all images on your system.</h4>  
```
docker images
```

<h4>Run a container</h4>
```
docker run busybox
docker run busybox echo "hello from busybox"
```

<h4>Show running containers</h4>
```
docker ps
```

<h4>Show containers that ran previously</h4>
```
docker ps -a
```

<h4>Live tty session</h4>
```
docker run -it busybox sh
```

<h4>Remove containers from which you left</h4>
--rm flag can be passed to docker run which automatically deletes the container once it's exited from  

```
docker rm $(docker ps -a -q -f status=exited)
```
or  
```
docker container prune
```

<h4>Run detached</h4>  
-d will detach our terminal  
-P will publish all exposed ports to random ports and finally  
--name corresponds to a name we want to give.  
```
docker run -d -P --name static-site name/static-site
```

<h4>See the ports by running the docker port [CONTAINER] command</h4>
```
docker port static-site
```

<h4>Specify a custom port</h4>
```
docker run -p 8888:80 prakhar1989/static-site
```

<h4>Stop a container</h4>
```
docker stop static-site
```

<h4>Creating an image</h4>  
A Dockerfile is a simple text-file that contains a list of commands that the Docker client calls while creating an image.  
CMD is to tell the container which command it should run when it is started  
port number that needs to be exposed  
specifying our base image. Use the FROM keyword to do that  
```
 Dockerfile
FROM python:3-onbuild

 tell the port number the container should expose
EXPOSE 5000

 run the command
CMD ["python", "./app.py"]
```

Dockerfile example
```
# Dockerfile  
FROM node:8  
WORKDIR /app  
COPY package.json /app  
RUN npm install  
COPY . /app  
EXPOSE 8081  
CMD node index.js
```

<h4>Build image from Dockerfile</h4>
```
docker build -t mz2kh/catnip .
```

<h4>Run the container</h4>
```
run -p 8888:5000 mz2kh/catnip
```
  
<h4>Publish image to Docker HUB</h4>
```
docker push mz2kh/catnip
```
  
Now that your image is online, anyone who has docker installed can play with your app by typing just a single command.  
```
docker run -p 8888:5000 prakhar1989/catnip
```

<h4>Search for images</h4>
```
docker search elasticsearch
```

<h4>When docker is installed, it creates three networks automatically.</h4>
```
docker network ls
NETWORK ID          NAME                DRIVER              SCOPE
77192b388b9d        bridge              bridge              local
3a125533ca3f        host                host                local
13e644755906        none                null                local
```

The bridge network is the network in which containers are run by default.  
<h4>Inspect bridge Network</h4>
```
docker network inspect bridge
```

<h4>Create our own network</h4>  
A bridge network allows containers connected to the same bridge network to communicate,  
while providing isolation from containers which are not connected to that bridge network. 
```
docker network create catnip-net
```

<h4>Launch containers into network (--net foodtrucks-net)</h4>
```
$ docker run -d --name es --net foodtrucks-net -p 9200:9200 -p 9300:9300 -e "discovery.type=single-node" docker.elastic.co/elasticsearch/elasticsearch:6.3.2
13d6415f73c8d88bddb1f236f584b63dbaf2c3051f09863a3f1ba219edba3673
$ docker network inspect foodtrucks-net
```

<h4>Create and run container on a created Network</h4>
./setup-docker.sh
```
!/bin/bash

build the flask container
docker build -t prakhar1989/foodtrucks-web .

create the network
docker network create foodtrucks-net

start the ES container
docker run -d --name es --net foodtrucks-net -p 9200:9200 -p 9300:9300 -e "discovery.type=single-node" docker.elastic.co/elasticsearch/elasticsearch:6.3.2

start the flask app container
docker run -d --net foodtrucks-net -p 5000:5000 --name foodtrucks-web prakhar1989/foodtrucks-web
```

Docker Registries & Repositories  
<h4>Searching an Image</h4>  
```
docker search nginx
docker search --filter stars=3 --no-trunc nginx
```

<h4>Pulling an Image</h4>
```
docker image pull nginx
docker image pull eon01/nginx localhost:5000/myadmin/nginx
```

<h4>Pushing an Image</h4>
```
docker image push eon01/nginx
docker image push eon01/nginx localhost:5000/myadmin/nginx
```
<h4>Running Containers`</h4>
Create and Run a Simple Container  
Start an ubuntu:latest image  
Bind the port 80 from the CONTAINER to port 3000 on the HOST  
Mount the current directory to /data on the CONTAINER  
```
docker container run --name infinite -it -p 3000:80 -v ${PWD}:/data ubuntu:latest
```

<h4>Creating a Container</h4>
```
docker container create -t -i eon01/infinite --name infinite
```

<h4>Running a Container</h4>
```
docker container run -it --name infinite -d eon01/infinite
```

<h4>Renaming a Container</h4>
```
docker container rename infinite infinity
```

<h4>Removing a Container</h4>
```
docker container rm infinite
```

<h4>Updating a Container</h4>
```
docker container update --cpu-shares 512 -m 300M infinite
```

<h4>Starting & Stopping Containers</h4>
```
docker container start nginx
```

```
docker container stop nginx
```


<h4>Restarting</h4>
```
docker container restart nginx
```

<h4>Pausing</h4>
```
docker container pause nginx
```

<h4>Unpausing</h4>
```
docker container unpause nginx
```

<h4>Blocking a Container</h4>
```
docker container wait nginx
```

<h4>Sending a SIGKILL</h4>
```
docker container kill nginx
```

<h4>Sending another signal</h4>
```
docker container kill -s HUP nginx
```

<h4>Connecting to an Existing Container</h4>
```
docker container attach nginx
```

<h4>Getting Information about Containers</h4>

<h4>Running Containers</h4>
```
docker container ls
docker container ls -a
```

<h4>Container Logs</h4>
docker logs infinite
Follow Container Logs
```
docker container logs infinite -f
```

<h4>Inspecting Containers</h4>
```
docker container inspect infinite
docker container inspect --format '{{ .NetworkSettings.IPAddress }}' $(docker ps -q)
```

<h4>Containers Events</h4>
```
docker system events infinite
```

<h4>Public Ports</h4>
```
docker container port infinite
```

<h4>Running Processes</h4>
```
docker container top infinite
```

<h4>Container Resource Usage</h4>
```
docker container stats infinite  
```

<h4>Inspecting changes to files or directories on a container’s filesystem</h4>
```
docker container diff infinite  
```

<h4>Manipulating Images</h4>

<h4>Listing Images</h4>
```
docker image ls
```

<h4>Building Images</h4>
```
docker build .
docker build github.com/creack/docker-firefox
docker build - < Dockerfile
docker build - < context.tar.gz
docker build -t eon/infinite .
docker build -f myOtherDockerfile .
curl example.com/remote/Dockerfile | docker build -f - .
```

<h4>Removing an Image</h4>
```
docker image rm nginx
```

<h4>Loading a Tarred Repository from a File or the Standard Input Stream</h4>
```
docker image load < ubuntu.tar.gz
docker image load --input ubuntu.tar
```

<h4>Save an Image to a Tar Archive</h4>
```
docker image save busybox > ubuntu.tar
```

<h4>Showing the History of an Image</h4>
```
docker image history
```

<h4>Creating an Image From a Container</h4>
```
docker container commit nginx
```

<h4>Tagging an Image</h4>
```
docker image tag nginx eon01/nginx
```

<h4>Pushing an Image</h4>
```
docker image push eon01/nginx
```

<h4>Creating Networks</h4>  
```
docker network create -d overlay MyOverlayNetwork
docker network create -d bridge MyBridgeNetwork
docker network create -d overlay \
  --subnet=192.168.0.0/16 \
  --subnet=192.170.0.0/16 \
  --gateway=192.168.0.100 \
  --gateway=192.170.0.100 \
  --ip-range=192.168.1.0/24 \
  --aux-address="my-router=192.168.1.5" --aux-address="my-switch=192.168.1.6" \
  --aux-address="my-printer=192.170.1.5" --aux-address="my-nas=192.170.1.6" \
  MyOverlayNetwork
```

<h4>Removing a Network</h4>
```
docker network rm MyOverlayNetwork
```

<h4>Listing Networks</h4>
```
docker network ls
```

<h4>Getting Information About a Network</h4>
```
docker network inspect MyOverlayNetwork
```

<h4>Connecting a Running Container to a Network</h4>
```
docker network connect MyOverlayNetwork nginx
```

<h4>Connecting a Container to a Network When it Starts</h4>
```
docker container run -it -d --network=MyOverlayNetwork nginx
```

<h4>Disconnecting a Container from a Network</h4>
```
docker network disconnect MyOverlayNetwork nginx
```

<h4>Exposing Ports</h4>  
Using Dockerfile, you can expose a port on the container using:
```
EXPOSE <port_number>
You can also map the container port to a host port using:

e.g.

docker run -p $HOST_PORT:$CONTAINER_PORT --name infinite -t infinite
```

<h4>Cleaning Docker</h4>  
<h4>Removing a Running Container </h4> 
```
docker container rm nginx
```

<h4>Removing a Container and its Volume</h4>
```
docker container rm -v nginx
```

<h4>Removing all Exited Containers</h4>
```
docker container rm $(docker container ls -a -f status=exited -q)
```

<h4>Removing All Stopped Containers</h4>
```
docker container rm `docker container ls -a -q`
```

<h4>Removing a Docker Image</h4>
```
docker image rm nginx
```

<h4>Removing Dangling Images</h4>
```
docker image rm $(docker image ls -f dangling=true -q)
```

<h4>Removing all Images</h4>
```
docker image rm $(docker image ls -a -q)
```

<h4>Removing all untagged images</h4>
```
docker image rm -f $(docker image ls | grep "^<none>" | awk "{print $3}")
```

<h4>Stopping & Removing all Containers</h4>
```
docker container stop $(docker container ls -a -q) && docker container rm $(docker container ls -a -q)
```

<h4>Removing Dangling Volumes</h4>
```
docker volume rm $(docker volume ls -f dangling=true -q)
```

<h4>Removing all unused (containers, images, networks and volumes)</h4>
```
docker system prune -f
```

<h4>Clean all</h4>
```
docker system prune -a
```
-->


<!--

***********************************************************************************************************************
* LINKS
***********************************************************************************************************************

Interview questions
https://github.com/sudheerj/reactjs-interview-questions#what-is-react

Callback, promises, async
https://medium.com/front-end-weekly/callbacks-promises-and-async-await-ad4756e01d90

Various links  
[Github pages markdown](https://help.github.com/articles/basic-writing-and-formatting-syntax/)  
[Recording Screen](https://github.com/phw/peek)  
[Site Point](https://www.sitepoint.com/)  
[Cheatsheets](https://devhints.io)  
[Github help](https://help.github.com/)  
[REST API Design Rulebook](https://pepa.holla.cz/wp-content/uploads/2016/01/REST-API-Design-Rulebook.pdf)  
[Static site generator](https://www.mkdocs.org)  
[Awesome frontend](https://github.com/sindresorhus/awesome#front-end-development)  
[Interview questions](https://github.com/MaximAbramchuck/awesome-interview-questions)  
[Deploy mkdocs to github](https://www.sitepoint.com/building-product-documentation-mkdocs/)  
[Mock socket](https://github.com/thoov/mock-socket)  
[Mock socket](https://stackoverflow.com/questions/42867183/mocking-websocket-in-jest)  
[Socket unit testing](https://medium.com/@ianovenden/react-redux-and-websocket-unit-testing-8c9236d4f3f6)  
[Socket+jest boilerplate](https://gist.github.com/tozwierz/76be651cc7a7d5c06ea290eec8a0ed73)  
[kubectl commands](https://kubernetes.io/docs/reference/kubectl/cheatsheet/)
[react forms](https://medium.com/@agoiabeladeyemi/the-complete-guide-to-forms-in-react-d2ba93f32825)

[jobs in netherland](https://www.honeypot.io/)

----------------------------------------------------------------------------------------------------------------------------------

React Table Links
https://codesandbox.io/s/github/tannerlinsley/react-table/tree/master/archives/v6-examples/react-table-cell-renderers
https://github.com/bvaughn/react-virtualized/issues/732
https://github.com/tannerlinsley/react-table/issues/786
https://stackoverflow.com/questions/56481459/render-table-cells-td-with-different-html-tags-in-react
https://www.npmjs.com/package/react-table
https://codesandbox.io/s/r5n96yvwnm
https://codesandbox.io/s/2vn8k07ymj?from-embed
https://codepen.io/aaronschwartz/pen/awOyQq?editors=0011)

----------------------------------------------------------------------------------------------------------------------------------

git immersion
http://gitimmersion.com/lab_01.html

----------------------------------------------------------------------------------------------------------------------------------


https://github.com/howtographql/react-apollo  
https://www.howtographql.com/react-apollo/0-introduction/  
https://github.com/treehouse-projects/intro-to-graphql/blob/master/s3v3.js  
https://www.howtographql.com/react-apollo/1-getting-started/
https://www.javascript.com/resources
https://github.com/rmotr/flask-api-example
https://www.digitalocean.com/community/tutorials/how-to-read-and-set-environmental-and-shell-variables-on-a-linux-vps
python https://www.programcreek.com
python https://www.geeksforgeeks.org
python https://www.journaldev.com/
https://www.fullstackpython.com/
https://realpython.com/
https://www.journaldev.com/17752/python-main-function
https://itnext.io/
CRUD https://www.djamware.com/post/59faec0a80aca7739224ee1f/building-crud-web-application-using-mern-stack
https://frontendmasters.com/books/front-end-handbook/2019/
https://dev.to/peterj/run-a-react-app-in-a-docker-container-kjn
https://searchstorage.techtarget.com/definition/all-flash-array
https://www.orosk.com/what-is-afa-all-flash-array/
https://reactjsexample.com
https://material-components.github.io/material-components-web-catalog/#/
https://cloud.google.com/kubernetes-engine/docs/tutorials/
https://github.com/kristoferjoseph/flexboxgrid
https://codepen.io/marcolago/pen/lqGFb

https://github.com/Mybridge/react-articles
https://github.com/Mybridge/react-articles/blob/master/src/02-2018.md
https://github.com/streamich/libreact
https://github.com/Oblosys/react-lifecycle-visualizer
https://www.react-spring.io/docs/hooks/examples
https://medium.mybridge.co/amazing-react-js-open-source-of-the-year-v-2019-364d057ac3f3

https://css-tricks.com/what-are-higher-order-components-in-react/


https://cssreference.io/
https://speckyboy.com/100-css-libraries-frameworks-tools/
https://scrimba.com/g/gR8PTE
https://scrimba.com
https://developer.mozilla.org/en-US/docs/Web/CSS/Layout_cookbook
https://grid.layoutit.com/
http://patrickbrosset.com/lab/2018-01-10-css-alignment-cheatsheet/
http://inanzzz.com
http://opensource.com
-->

<!--
***********************************************************************************************************************
* INTERVIEW QUESTIONS
***********************************************************************************************************************

<h4>Event delegation</h4>
Event delegation is a technique involving adding event listeners to a parent element instead of adding them to the descendant elements. 

<h4>How this works in JavaScript</h4>
It depends on the contxt.
In case of Explicit Binding we explicitly say to a function what object it should use for this .

<h4>Prototypal inheritance</h4>
Every single JavaScript object has a property, called prototype, which points to a different object.
When a property is accessed on an object and if the property is not found on that object, the JavaScript engine looks at the object's prototype, and the prototype's prototype and so on.

<h4>What is IIFE</h4>
IIFE stands for Immediately Invoked Function Expressions.

<h4>What's the difference between a variable that is: null, undefined or undeclared?</h4>
undeclared: without using var, let or const.
undefined: declared, but not assigned a value.
null: explicitly assigned to the null value.

<h4>What is a closure</h4>
A closure gives you access to an outer function’s scope from an inner function.
To avoid the usage of global variables, use the local variables and wrap your code in the closure.
The closure closes over a block of code in order to hide it from the "outside world"s.

<h4>Difference between a .forEach loop and a .map() loop</h4>
.map() returns a new array.
forEach
Iterates through the elements in an array.
Executes a callback for each element.
Does not return a value.
```
const a = [1, 2, 3];
const doubled = a.forEach((num, index) => {
  // Do something with num and/or index.
});
// doubled = undefined
```

map
Iterates through the elements in an array.
"Maps" each element to a new element by calling the function on each element, creating a new array as a result.
```
const a = [1, 2, 3];
const doubled = a.map(num => {
  return num * 2;
});
// doubled = [2, 4, 6]
```

<h4>use case for anonymous functions?</h4>
As a callback that is used once and does not need to be used anywhere else.
```
setTimeout(function() {
  console.log('Hello world!');
}, 1000);
```

<h4>How do you organize your code?</h4>
I use React/Redux which utilize a single-directional data flow based on Flux architecture.

<h4>Difference between host objects and native objects?</h4>
Native: Ecmas script specification (String, Math, RegExp, Object, Function)
Host: are provided by the runtime environment (browser or Node), such as window, XMLHTTPRequest
-->


<!-- 

***********************************************************************************************************************
* KUBERNETES
***********************************************************************************************************************

Terraform enables users to define and provision a datacenter infrastructure using a high-level configuration language known as Hashicorp Configuration Language (HCL), or optionally JSON.  
  
Terragrunt is a thin wrapper for Terraform that provides extra tools for keeping your Terraform configurations DRY.  

Helm helps you manage Kubernetes applications — Helm Charts help you define, install, and upgrade even the most complex Kubernetes application.  

In a containerized architecture, the different services that constitute an application are packaged into separate containers and deployed across a cluster of physical or virtual machines.  
K8s automates the deployment, management, scaling, networking, and availability of container-based applications.

Cluster: The highest-level Kubernetes abstraction, the cluster, refers to the group of machines running Kubernetes.  
Nodes: Each cluster contains Kubernetes nodes. Nodes might be physical machines or VMs.  
Pods: add a layer of abstraction to grouped containers, which helps you schedule workloads and provide necessary services—like networking and storage—to those containers.  
Each pod represents a single instance of an application or running process in Kubernetes, and consists of one or more containers.  
Service: A service in Kubernetes describes how a given group of pods (or other Kubernetes objects) can be accessed via the network.  
The controller manager ensures that the state of the system—applications, workloads, etc.—matches the desired state defined in Etcd’s configuration settings. Ingress is an API that manages external access to a cluster’s services, typically via HTTP.  
Minikube is a tool for running a single-node Kubernetes cluster inside a VM.

One of the most basic duties Kubernetes takes off your hands is the busywork of keeping an application up, running, and responsive to user demands. Apps that become “unhealthy,” or don’t conform to the definition of health you describe for them, can be automatically healed.  
Maximize hardware resources needed to run your enterprise apps.  
Helm is essentially a package manager for Kubernetes.  

On-disk files in a Container are ephemeral, which presents some problems for non-trivial applications.  
Kubernetes provides abstractions to allow containers and apps to deal with storage in the same decoupled way as other resources. Many common kinds of storage, from Amazon EBS volumes to plain old NFS shares, can be accessed via Kubernetes storage drivers, called volumes.  

Kubernetes also needs to integrate with networking, storage, security, telemetry and other services to provide a comprehensive container infrastructure.  

With the help of other open source projects like heapster you can orchestrate all parts of your container infrastructure.  
  
With Kubernetes you can:  
  
Manage containers across multiple hosts.  
Maximize hardware resources needed to run your enterprise apps.  
Control and automate application deployments and updates.  
Mount and add storage to run stateful apps.  
Scale containerized applications and their resources on the fly.  
Declaratively manage services, which guarantees the deployed applications are always running how you deployed them.  
Health-check and self-heal your apps with autoplacement, autorestart, autoreplication, and autoscaling.  
  
Kubernetes, however, relies on other projects to fully provide these orchestrated services.  
  
Kubernetes glossary:  
https://kubernetes.io/docs/reference/glossary/?fundamental=true  
https://towardsdatascience.com/key-kubernetes-concepts-62939f4bc08e  
https://medium.freecodecamp.org/learn-kubernetes-in-under-3-hours-a-detailed-guide-to-orchestrating-containers-114ff420e882  
https://matthewpalmer.net/kubernetes-app-developer/#purchase-the-ebook  
  
Kubernetes links:  
Playing with Local Kubernetes Cluster:  
https://medium.com/@georgelai/minikube-playing-with-local-kubernetes-cluster-d93e3e4a1ddf  

https://serverless.css-tricks.com/

https://www.linux.org

https://codeburst.io/javascript-essentials-objects-56373a1a6bfb

.js or .jsx https://github.com/airbnb/javascript/pull/985
-->


<!-- 
<ReactTable data={{...}} className="-striped -highlight" defaultSortDesc={true} getTrProps={[Function: getTrProps]} columns={{...}} defaultPageSize={5} resolveData={[Function: resolveData]} loading={false} showPagination={true} showPaginationTop={false} showPaginationBottom={true} showPageSizeOptions={true} pageSizeOptions={{...}} defaultPage={0} showPageJump={true} collapseOnSortingChange={true} collapseOnPageChange={true} collapseOnDataChange={true} freezeWhenExpanded={false} sortable={true} multiSort={true} resizable={true} filterable={false} defaultSorted={{...}} defaultFiltered={{...}} defaultResized={{...}} defaultExpanded={{...}} defaultFilterMethod={[Function: defaultFilterMethod]} defaultSortMethod={[Function: defaultSortMethod]} onPageChange={[undefined]} onPageSizeChange={[undefined]} onSortedChange={[undefined]} onFilteredChange={[undefined]} onResizedChange={[undefined]} onExpandedChange={[undefined]} pivotBy={[undefined]} pivotValKey="_pivotVal" pivotIDKey="_pivotID" subRowsKey="_subRows" aggregatedKey="_aggregated" nestingLevelKey="_nestingLevel" originalKey="_original" indexKey="_index" groupedByPivotKey="_groupedByPivot" onFetchData={[Function: onFetchData]} style={{...}} getProps={[Function: emptyObj]} getTableProps={[Function: emptyObj]} getTheadGroupProps={[Function: emptyObj]} getTheadGroupTrProps={[Function: emptyObj]} getTheadGroupThProps={[Function: emptyObj]} getTheadProps={[Function: emptyObj]} getTheadTrProps={[Function: emptyObj]} getTheadThProps={[Function: emptyObj]} getTheadFilterProps={[Function: emptyObj]} getTheadFilterTrProps={[Function: emptyObj]} getTheadFilterThProps={[Function: emptyObj]} getTbodyProps={[Function: emptyObj]} getTrGroupProps={[Function: emptyObj]} getTdProps={[Function: emptyObj]} getTfootProps={[Function: emptyObj]} getTfootTrProps={[Function: emptyObj]} getTfootTdProps={[Function: emptyObj]} getPaginationProps={[Function: emptyObj]} getLoadingProps={[Function: emptyObj]} getNoDataProps={[Function: emptyObj]} getResizerProps={[Function: emptyObj]} column={{...}} expanderDefaults={{...}} pivotDefaults={{...}} previousText="Previous" nextText="Next" loadingText="Loading..." noDataText="No rows found" pageText="Page" ofText="of" rowsText="rows" pageJumpText="jump to page" rowsSelectorText="rows per page" TableComponent={[Function: TableComponent]} TheadComponent={[Function: cmp]} TbodyComponent={[Function: cmp]} TrGroupComponent={[Function: TrGroupComponent]} TrComponent={[Function: TrComponent]} ThComponent={[Function: ThComponent]} TdComponent={[Function: TdComponent]} TfootComponent={[Function: cmp]} FilterComponent={[Function: FilterComponent]} ExpanderComponent={[Function: ExpanderComponent]} PivotValueComponent={[Function: PivotValueComponent]} AggregatedComponent={[Function: AggregatedComponent]} PivotComponent={[undefined]} PaginationComponent={[Function: ReactTablePagination]} PreviousComponent={[undefined]} NextComponent={[undefined]} LoadingComponent={[Function: LoadingComponent]} NoDataComponent={[Function: cmp]} ResizerComponent={[Function: cmp]} PadRowComponent={[Function: PadRowComponent]} />
 -->
