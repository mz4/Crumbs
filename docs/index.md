# TOOLS  
---

## GIT

<h3>Install git</h3>
```
sudo apt-get update
sudo apt-get upgrade
sudo apt-get install git
git --version
```

<h3>Create a New Git Repository from scratch</h3>
```
mkdir to create a directory to contain the project.
cd into the new directory.
git init.
Write code. (The first file to create is probably a ReadMe file)
git add to add the files.
git commit
```

<h3>Create New Git Repository from existing project</h3>
```
cd into the directory containing the project.
git init.
git add to add all of the relevant files.
create a .gitignore to indicate all of the files you don’t want to track
git commit.
```

<h3>Connect to github</h3>
```
Go to github.
Log in to your account.
Click the new repository button in the top-right. 
Click the “Create repository” button.
git remote add origin git@github.com:username/new_repo
git push -u origin master
```

<h3>Create, switch and push origin new branch</h3>
```
git checkout -b issue400-master
git push -u origin issue400-master
```

<h3>Add, Commit and Push</h3>
```
git add sys_ui/css/FILE.css 
git add sys_ui/FILE.html 
git add app/dir/ 
git commit
git push
```

<h3>Squash commits</h3>
```
git reset --soft HEAD~$squashCount
git commit -m "$commitMsg"
```

<h3>Delete a local and remote branch</h3>
```
git branch -d branch_name
git push origin --delete <branch_name>
```

<h3>Clone repo</h3>
```
git clone USER@10.0.2.10:/home/git/repos/sys .
```

<h3>Clone specific branch</h3>
```
git clone -b <branch> <remote_repo>
git clone -b my-branch git@github.com:user/myproject.git
```

<h3>Show current branch</h3>
```
git branch
```

<h3>Show local and remote branch</h3>
```
git branch -a
```

<h3>Check Status</h3>
```
git status
```

<h3>Check Log</h3>
```
git log
```

<h3>Edit Last Commit Message</h3>
```
git commit --amend -m "New commit message"
```

<h3>Log commit subject of last 10 commits</h3>
```
git log -10 --pretty=format:"%h %s"
```

<h3>Single file history</h3>
```
git log -p filename
```

<h3>Get tag</h3>
```
git log --decorate v0.4bugfix|head -n1|sed 's/.*tag: //;s/[^a-zA-Z.0-9].*//'
```

<h3>Get commits by date and author</h3>
```
git log --pretty=format:"%ad - %an: %s" --after="2010-02-15" --until="2018-08-20" --author="John"
```

<h3>Get number of commits by author</h3>
```
git shortlog -s -n --all
```

<h3>Remove local untracked files</h3>
```
git clean -fdx
```

<h3>Undo last commit.</h3>
Warning: Don't do this if you've already pushed
```
 git reset HEAD~
```

<h3>Undo last commit.</h3>
If you don't want the changes and blow everything away:
Warning: Don't do this if you've already pushed
```	
 git reset --hard HEAD~
```

<h3>Untrack .pyc files</h3>
```
$ find . -name '*.pyc' | xargs -n 1 git rm --cached
```

<h3>Switch to branch</h3>
```
git checkout BRANCHNAME
```

<h3>Pull from master branch</h3>
```
git pull origin master
```

<h3>Checkout master</h3>
```
git chekcout master
```

<h3>Merge branch into master</h3>
```
git checkout master
git merge user_interface
```

<h3>Create Tags</h3>
```
git tag v1.0 ec32d32
git push origin --tags
```

<h3>Undo a local commit</h3>
```
git reset --soft HEAD^     # use --soft if you want to keep your changes
git reset --hard HEAD^     # use --hard if you don't care about keeping the changes you made
```

<h3>Undo git add</h3>
```
git reset filename.jsx
```

<h3>Show differences after git pull</h3>
```
git diff master@{1} master
```

<h3>Lists branches merged into master</h3>
```
git branch --merged master
```

<h3>Lists branches merged into HEAD</h3>
```
git branch --merged 
```

<h3>Lists branches that have not been merged</h3>
```
git branch --no-merged
```

<h3>Checkout previous branch</h3>
```
git checkout -
```

<h3>Diff between branches</h3>
Diff between current branch and master:  
```
git diff master
```

<h3>Diff between two branches:</h3>
```
git diff master..staging
```

<h3>Show only files that are different between the two branches</h3>
```
git diff --name-status master..staging
```

<h3>Create New Branch and Checkout – In One Command</h3>
```
git checkout -b <branch_name>
```

<h3>Revert Changes to File</h3>
```
git checkout -- <file>
```

<h4>Squashing commits into one</h4>
to maintain a clean commit log message when merging the remote branch to master.

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

---

## LINUX TIPS

Systems Directories
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

Most used Commands
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

Process Management
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

File permission
```
chmod octal file Change the permission of file to octal,which can be found separately for user,group,world by adding,
• 4-read(r)
• 2-write(w)
• 1-execute(x)
```
Find how many lines for file extension
```
wc `find | grep jsx$`
```

truncate file content
```
truncate -s 0 dash.txt
```

cat long file
```
cat branch | more -d
```

Check if port is listening
```
sudo netstat -ntlp | grep :443
```
Find a string
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
Directory Size
```
du -hs direcotryName
```
Show system name and kernel
```
uname -a
```
Start a screen session.
```
screen
```
Resume a screen session.
```
screen -r
```
List screen sessions.
```
screen -list
```
List All Available Packages
```
apt-cache pkgnames
```
Package Name and Description of Software
```
apt-cache search vsftpd
```
Package Information
```
apt-cache show netcat
```
Dependencies for Specific Packages
```
apt-cache showpkg vsftpd
```
Update System Packages
```
sudo apt-get update
```
Clean up disks space
```
sudo apt-get clean
```
Download only source code
```
sudo apt-get --download-only source vsftpd
```
Check broken dependencies
```
sudo apt-get check
```
Remove files containing a string
```
rm ?*foo?*
ls -d '*foo*' | egrep -v '^foo|foo$' | xargs rm
```
Create folder and cd into it
```
mkdir foo && cd "$_"
```

Create Swap file
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

Change permission in filder and files
```
Chmod chown
find . -type d -exec chmod 777 {} +
find . -type f -exec chmod 777 {} +
```

Mount/Unmount
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

Compress/Uncompress  Files
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
grep "t[wo]o" GPL-3 //By placing a group of characters within brackets ("[" and "]"), we can specify that the character at that position can be any one character found within the bracket group.

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

---

## NODE / NPM  

version
```
which node
which npm
node --version
npm --version
```

global install packages
```
npm install uglify-js --global
```

list global packages
```
npm list --global
npm list -g --depth=0
```

initialize project
```
npm init
```

local install packages devDependencies
```
npm install should --save-dev
```

local install packages dependencies
```
npm install should --save
```

uninstall packages
```
npm uninstall underscore
```

install specific version
```
npm install underscore@1.8.2
```

check outdated packages
```
npm outdated
```

update packages
```
npm update underscore
```

Quick Project Setup - React, Webpack, Babel, ESLint
  
Dependencies
```
npm install --save react react-dom
```

Dev Dependencies
```
npm install --save-dev babel-{core,loader} babel-preset-es2015 babel-preset-react babel-eslint css-loader node-sass sass-loader style-loader file-loader webpack webpack-dev-server eslint eslint-plugin-import eslint-plugin-react eslint-watch
```

NPM Scripts (package.json)
```
"scripts": {
  "start": "webpack-dev-server --progress --hot --inline",
  "build": "webpack",
  "lint": "esw webpack.config.js src",
  "lint:watch": "npm run lint -- --watch",
  "fix": "./node_modules/.bin/eslint src --fix"
},
```

NVM: manage different versions of Node:
```
$ curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.33.0/install.sh | bash
```

```
$ export NVM_DIR=”$HOME/.nvm”
$ [ -s “$NVM_DIR/nvm.sh” ] && \. “$NVM_DIR/nvm.sh”
$ [ -s "$NVM_DIR/bash_completion" ] && \.   "$NVM_DIR/bash_completion"
```

Install a new version
```
nvm install 8.9.4
```

Show available versions of node
```
nvm ls
```

Use a particular version
```
nvm use 10.15.3
```


Babel (.babelrc)
```
{
  "presets": [
    "es2015",
    "react"
  ]
}
```

## WEBPACK

webpack installation
```
npm install --save-dev webpack
```
If you're using webpack v4 or later, you'll need to install the CLI.  
```
npm install --save-dev webpack-cli
```
Create a webpack config file e.g. webpack.config.js  
```
const path = require('path');

module.exports = {
  entry: './src/index.js',
  output: {
    filename: 'main.js',
    path: path.resolve(__dirname, 'dist')
  }
};
```
in package.json  
```
 "scripts": {
      "build": "webpack"
    },
```

Webpack Performance codesplitting react-loadable
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

general performance improvements
```
React-loadable: this is a code splitting library. It allows to load components only when those are needed.  
There are 2 main ways to split code:  
by route
by subcomponents

Show loading icon when initial page is loading.
The objective in this case is to give immediately a feedback to the user that page is loading.

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

Docker terminology
- Images: The blueprints of our application which form the basis of containers.  
- Containers: Created from Docker images and run the actual application. 
- Docker Daemon: The background service running on the host that manages building, running and distributing Docker containers. 
- Docker Client: The command line tool that allows the user to interact with the daemon. 
- Docker Hub: A registry of Docker images. If required, one can host their own Docker registries and can use them for pulling images.
  
- Base images: are images that have no parent image, usually images with an OS like ubuntu, busybox or debian.  
- Child images: are images that build on base images and add additional functionality.  
  
- Official images: are images that are officially maintained and supported by the folks at Docker. These are typically one word long.  
- User images: images created and shared by users. They build on base images and add additional functionality. Typically, these are formatted as user/image-name.  
  
Install latest Docker  
```
sudo apt-get install docker-ce
```

Test your Docker installation by running the following  
```
docker run hello-world
```
  
The pull command fetches image from the Docker registry and saves it to system.  
```
docker pull busybox
```

Docker Hub  
[Docker Images hub](https://hub.docker.com/search/?q=&type=image)  

to see a list of all images on your system.  
```
docker images
```

run a container
```
docker run busybox
docker run busybox echo "hello from busybox"
```

show running containers
```
docker ps
```

show containers that ran previously
```
docker ps -a
```

live tty session
```
docker run -it busybox sh
```

Remove containers from which you left
```
docker rm $(docker ps -a -q -f status=exited)
OR
docker container prune
```

--rm flag can be passed to docker run which automatically deletes the container once it's exited from  

Run detached  
-d will detach our terminal  
-P will publish all exposed ports to random ports and finally  
--name corresponds to a name we want to give.  
```
docker run -d -P --name static-site name/static-site
```

See the ports by running the docker port [CONTAINER] command
```
docker port static-site
```

Specify a custom port
```
docker run -p 8888:80 prakhar1989/static-site
```

Stop a container
```
docker stop static-site
```

Creating an image  
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

Build image from Dockerfile
```
docker build -t mz2kh/catnip .
```

Run the container
```
run -p 8888:5000 mz2kh/catnip
```
  
Publish image to Docker HUB
```
docker push mz2kh/catnip
```
  
Now that your image is online, anyone who has docker installed can play with your app by typing just a single command.  
```
docker run -p 8888:5000 prakhar1989/catnip
```

Search for images
```
docker search elasticsearch
```

When docker is installed, it creates three networks automatically.
```
docker network ls
NETWORK ID          NAME                DRIVER              SCOPE
77192b388b9d        bridge              bridge              local
3a125533ca3f        host                host                local
13e644755906        none                null                local
```

The bridge network is the network in which containers are run by default.  
Inspect bridge Network:
```
docker network inspect bridge
```

Create our own network  
A bridge network allows containers connected to the same bridge network to communicate,  
while providing isolation from containers which are not connected to that bridge network. 
```
docker network create catnip-net
```

Launch containers into network (--net foodtrucks-net)
```
$ docker run -d --name es --net foodtrucks-net -p 9200:9200 -p 9300:9300 -e "discovery.type=single-node" docker.elastic.co/elasticsearch/elasticsearch:6.3.2
13d6415f73c8d88bddb1f236f584b63dbaf2c3051f09863a3f1ba219edba3673
$ docker network inspect foodtrucks-net
```

Create and run container on a created Network  
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
Searching an Image  
```
docker search nginx
docker search --filter stars=3 --no-trunc nginx
```
Pulling an Image
```
docker image pull nginx
docker image pull eon01/nginx localhost:5000/myadmin/nginx
```
Pushing an Image
```
docker image push eon01/nginx
docker image push eon01/nginx localhost:5000/myadmin/nginx
```
Running Containers  
Create and Run a Simple Container  
Start an ubuntu:latest image  
Bind the port 80 from the CONTAINER to port 3000 on the HOST  
Mount the current directory to /data on the CONTAINER  
```
docker container run --name infinite -it -p 3000:80 -v ${PWD}:/data ubuntu:latest
```

Creating a Container  
```
docker container create -t -i eon01/infinite --name infinite
```
Running a Container  
```
docker container run -it --name infinite -d eon01/infinite
```
Renaming a Container  
```
docker container rename infinite infinity
```
Removing a Container
```
docker container rm infinite
```
Updating a Container
```
docker container update --cpu-shares 512 -m 300M infinite
```

Starting & Stopping Containers  
Starting  
```
docker container start nginx
```

Stopping
```
docker container stop nginx
```
Restarting
```
docker container restart nginx
```
Pausing
```
docker container pause nginx
```
Unpausing
```
docker container unpause nginx
```
Blocking a Container
```
docker container wait nginx
```
Sending a SIGKILL
```
docker container kill nginx
```
Sending another signal
```
docker container kill -s HUP nginx
```
Connecting to an Existing Container
```
docker container attach nginx
```
Getting Information about Containers
Running Containers
```
docker container ls
docker container ls -a
```
Container Logs
docker logs infinite
Follow Container Logs
```
docker container logs infinite -f
```
Inspecting Containers
```
docker container inspect infinite
docker container inspect --format '{{ .NetworkSettings.IPAddress }}' $(docker ps -q)
```
Containers Events
```
docker system events infinite
```
Public Ports
```
docker container port infinite
```
Running Processes
```
docker container top infinite
```
Container Resource Usage  
```
docker container stats infinite  
```
Inspecting changes to files or directories on a container’s filesystem  
```
docker container diff infinite  
```
Manipulating Images  
Listing Images  
```
docker image ls
```
Building Images  
```
docker build .
docker build github.com/creack/docker-firefox
docker build - < Dockerfile
docker build - < context.tar.gz
docker build -t eon/infinite .
docker build -f myOtherDockerfile .
curl example.com/remote/Dockerfile | docker build -f - .
```
Removing an Image  
```
docker image rm nginx
```
Loading a Tarred Repository from a File or the Standard Input Stream
```
docker image load < ubuntu.tar.gz
docker image load --input ubuntu.tar
```
Save an Image to a Tar Archive
```
docker image save busybox > ubuntu.tar
```
Showing the History of an Image
```
docker image history
```
Creating an Image From a Container
```
docker container commit nginx
```
Tagging an Image
```
docker image tag nginx eon01/nginx
```
Pushing an Image
```
docker image push eon01/nginx
```
Networking  
Creating Networks  
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
Removing a Network
```
docker network rm MyOverlayNetwork
```
Listing Networks
```
docker network ls
```
Getting Information About a Network
```
docker network inspect MyOverlayNetwork
```
Connecting a Running Container to a Network
```
docker network connect MyOverlayNetwork nginx
```
Connecting a Container to a Network When it Starts
```
docker container run -it -d --network=MyOverlayNetwork nginx
```
Disconnecting a Container from a Network
```
docker network disconnect MyOverlayNetwork nginx
```
Exposing Ports  
Using Dockerfile, you can expose a port on the container using:
```
EXPOSE <port_number>
You can also map the container port to a host port using:

e.g.

docker run -p $HOST_PORT:$CONTAINER_PORT --name infinite -t infinite
```

Cleaning Docker  
Removing a Running Container  
```
docker container rm nginx
```
Removing a Container and its Volume
```
docker container rm -v nginx
```
Removing all Exited Containers
```
docker container rm $(docker container ls -a -f status=exited -q)
```
Removing All Stopped Containers
```
docker container rm `docker container ls -a -q`
```
Removing a Docker Image
```
docker image rm nginx
```
Removing Dangling Images
```
docker image rm $(docker image ls -f dangling=true -q)
```
Removing all Images
```
docker image rm $(docker image ls -a -q)
```
Removing all untagged images
```
docker image rm -f $(docker image ls | grep "^<none>" | awk "{print $3}")
```
Stopping & Removing all Containers
```
docker container stop $(docker container ls -a -q) && docker container rm $(docker container ls -a -q)
```
Removing Dangling Volumes
```
docker volume rm $(docker volume ls -f dangling=true -q)
```
Removing all unused (containers, images, networks and volumes)
```
docker system prune -f
```
Clean all
```
docker system prune -a
```
---

## VS Code
<h3>Debug code through Chrome Debugger extension</h3>
Launch VS Code Quick Open (Ctrl+P), paste the following command, and press enter.  
```
ext install msjsdiag.debugger-for-chrome
```

<h3>Create a launch file for the Visual Studio Code Debugger.</h3>
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
<!--
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
https://dev.to/peterj/run-a-react-app-in-a-docker-container-kjn
-->

