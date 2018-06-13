# git_basics
Described the basics of git

<p align="center">
  <a>
    <img  src="https://www.ithands.com/blog/wp-content/uploads/2016/10/ITH_Managing-Code-in-GIT.jpg">
  </a>
  <p align="center">** Hands-on Git **</p>
</p>

## Git

<p>Git is a distributed revision control and source code management system with an emphasis on speed.</p>
<p>Git was initially designed and developed by Linus Torvalds for Linux kernel development.</p>
<p>Git is a free software distributed under the terms of the GNU General Public License version 2.</p>

## Version Control System(VCS)

VCS is a software that helps software developers to work together and maintain a complete history of their work.

<p>Listed below are the functions of a VCS:</p>

<ul>
<li>Allows developers to work simultaneously.</li>
<li>Does not allow overwriting each other’s changes.</li>
<li>Maintains a history of every version.</li>
</ul>

### Following are the types of VCS:
<ol>
  <li>Centralized version control system (CVCS).</li>
  <li>Distributed/Decentralized version control system (DVCS).</li>
</ol>


### Difference between CVCS v/s DVCS:
Distributed version control systems (DVCSs) solve different problems than Centralized VCSs. Comparing them is like comparing hammers and screwdrivers.

<h3>CVCS: </h3>
<p>systems are designed with the intent that there is One True Source that is Blessed, and therefore Good. All developers work (checkout) from that source, and then add (commit) their changes, which then become similarly Blessed. The only real difference between CVS, Subversion, ClearCase, Perforce, VisualSourceSafe and all the other CVCSes is in the workflow, performance, and integration that each product offers.</p>

<h3>DVCS: </h3>
<p>
systems are designed with the intent that one repository is as good as any other, and that merges from one repository to another are just another form of communication. Any semantic value as to which repository should be trusted is imposed from the outside by process, not by the software itself.
</p>
<p>
The real choice between using one type or the other is organizational -- if your project or organization wants centralized control, then a DVCS is a non-starter. If your developers are expected to work all over the country/world, without secure broadband connections to a central repository, then DVCS is probably your salvation.
</p>

## Advantages of Git
<ol>
<li>Free and open source</li>
<li>Fast and small</li>
<li>Implicit backup</li>
<li>Security</li>
<li>No need of powerful hardware</li>
<li>Easier branching</li>
</ol>

### Security
<p>Git uses a common cryptographic hash function called secure hash function (SHA1), to name and identify objects within its database. Every file and commit is check-summed and retrieved by its checksum at the time of checkout. It implies that, it is impossible to change file, date, and commit message and any other data from the Git database without knowing Git.</p>


## DVCS Terminologies

<h3>Local Repository </h3>
<p>Every VCS tool provides a private workplace as a working copy. Developers make changes in their private workplace and after commit, these changes become a part of the repository. Git takes it one step further by providing them a private copy of the whole repository. Users can perform many operations with this repository such as add file, remove file, rename file, move file, commit changes, and many more.</p>

<h3>Working Directory and Staging Area or Index</h3>
<p>The working directory is the place where files are checked out. In other CVCS, developers generally make modifications and commit their changes directly to the repository. But Git uses a different strategy. Git doesn’t track each and every modified file. Whenever you do commit an operation, Git looks for the files present in the staging area. Only those files present in the staging area are considered for commit and not all the modified files.</p>

### Basic flow:
<ol>
<li>User can modify the file in the local repository.</li>
<li>Add the modified files to the staging area.</li>
<li>And perform commit operation that moves the files from the staging area. After push operation, it stores the changes permanently to the Git repository.</li>
</ol>

<p style="align: center;">
<img src="https://reganmusic.files.wordpress.com/2016/07/gitflow.jpeg" alt="Algorithm git flow" />
</p>


### Example

<p>I modified a file called test.js and want to push to the remote by staging and committing.</p>

```js
#First add the files
git add test.js

#adds file to the staging area
git commit -m "Added test scenarios in the test.js file"

#push to the remote server now
git push origin master
```

## Blobs
<p>Blob stands for <b>Binary Large Object</b>. Each version of a file is represented by blob. A blob holds the file data but doesn’t contain any metadata about the file. It is a binary file, and in Git database, it is named as SHA1 hash of that file. In Git, files are not addressed by names. Everything is content-addressed.</p>

## Trees
<p>Tree is an object, which represents a directory. It holds blobs as well as other sub-directories. A tree is a binary file that stores references to blobs and trees which are also named as SHA1 hash of the tree object.</p>

## Commits
<p>Commit holds the current state of the repository. A commit is also named by SHA1 hash. You can consider a commit object as a node of the linked list. Every commit object has a pointer to the parent commit object. From a given commit, you can traverse back by looking at the parent pointer to view the history of the commit. If a commit has multiple parent commits, then that particular commit has been created by merging two branches.</p>

## Branches
<p>
Branches are used to create another line of development. By default, Git has a master branch, which is same as trunk in Subversion. Usually, a branch is created to work on a new feature. Once the feature is completed, it is merged back with the master branch and we delete the branch. Every branch is referenced by HEAD, which points to the latest commit in the branch. Whenever you make a commit, HEAD is updated with the latest commit.
</p>

## Tags
<p>
Tag assigns a meaningful name with a specific version in the repository. Tags are very similar to branches, but the difference is that tags are immutable. It means, tag is a branch, which nobody intends to modify. Once a tag is created for a particular commit, even if you create a new commit, it will not be updated. Usually, developers create tags for product releases.
</p>

## Clone
<p>
Clone operation creates the instance of the repository. Clone operation not only checks out the working copy, but it also mirrors the complete repository. Users can perform many operations with this local repository. The only time networking gets involved is when the repository instances are being synchronized.
</p>

## Pull
</p>Pull operation copies the changes from a remote repository instance to a local one. The pull operation is used for synchronization between two repository instances. This is same as the update operation in Subversion.</p>

## Push
<p>
Push operation copies changes from a local repository instance to a remote one. This is used to store the changes permanently into the Git repository. This is same as the commit operation in Subversion.
</p>

## HEAD
<p>
HEAD is a pointer, which always points to the latest commit in the branch. Whenever you make a commit, HEAD is updated with the latest commit. The heads of the branches are stored in <b>.git/refs/heads/</b> directory.
</p>

## Revision
<p>Revision represents the version of the source code. Revisions in Git are represented by commits. These commits are identified by SHA1 secure hashes.</p>

## URL
URL represents the location of the Git repository. Git URL is stored in config file.

## Git - Environment Setup

### Installation of Git Client

```js
[ubuntu ~]$ sudo apt-get install git-core
[sudo] password for ubuntu:

[ubuntu ~]$ git --version
git version 2.15.1
```

### Customize Git Environment
<p>
Git provides the git config tool, which allows you to set configuration variables. Git stores all global configurations in .gitconfig file, which is located in your home directory. To set these configuration values as global, add the --global option, and if you omit --global option, then your configurations are specific for the current Git repository.
</p>

<p>
You can also set up system wide configuration. Git stores these values in the /etc/gitconfig file, which contains the configuration for every user and repository on the system. To set these values, you must have the root rights and use the --system option.
</p>

<h4>Setting username: </h4>

```js
$ git config --global user.name "Git user"
```

<h4>Setting email id: </h4>

```js
$ git config --global user.email "gituser@xyz.com"
```

<h4>Avoid merge commits for pulling: </h4>
<p>
You pull the latest changes from a remote repository, and if these changes are divergent, then by default Git creates merge commits. We can avoid this via following settings.
</p>

```js
$ git config --global branch.autosetuprebase always
```

<h4>Color highlighting: </h4>
<p>
The following commands enable color highlighting for Git in the console.
</p>

```js
$ git config --global color.ui true

$ git config --global color.status auto

$ git config --global color.branch auto
```

<h4>Setting default editor: </h4>

```js
$ git config --global core.editor vim
```

<h4>Setting default merge tool: </h4>

```js
$ git config --global merge.tool vimdiff
```

<h4>Listing Git settings: </h4>

```js
$ git config --list

//output
user.name=Git user
user.email=gituser@xyz.com
push.default=nothing
branch.autosetuprebase=always
color.ui=true
color.status=auto
color.branch=auto
core.editor=vim
merge.tool=vimdiff
```

## Git - Life Cycle

<ul>
<li>Clone the git repository as the working copy.</li>
<li>Modify the working copy.</li>
<li>Review the changes before commit.</li>
<li>Commit the changes and push the code to the remote repository.</li>
<li>Commit the changes and feels like changing again, modify the changes, commit again and push the changes.</li>
</ul>

<p style ="align:center;">
<img src="https://upload.wikimedia.org/wikipedia/commons/2/29/Git_data_flow.png" alt="Git Life Cycle"></img>
</p>

## Git - Create Operation

### Create New User

```js
# add new group
groupadd dev

# add new user
useradd -G devs -d /home/gituser -m -s /bin/bash gituser

# change password
passwd gituser



//Output of the above command will produce
Changing password for user gituser.
New password:
Retype new password:
passwd: all authentication token updated successfully.
```

### Create a Bare Repository

<p>Let us initialize a new repository by using <b>init</b> command followed by <b>--bare</b> option. It initializes the repository without a working directory. By convention, the bare repository must be named as <b>.git</b>.</p>

```js
$ pwd
/home/gituser

$ mkdir project.git

$ cd project.git/

$ ls

$ git --bare init
Initialized empty Git repository in /home/gituser-m/project.git/

$ ls
branches config description HEAD hooks info objects refs

```

### Push Changes to the Repository

```js
$ pwd
/home/gituser

$ mkdir gituser_repo

$ cd gituser_repo/

$ git init
Initialized empty Git repository in /home/gituser/gituser_repo/.git/

$ echo 'TODO: Add contents for README' > README

$ git status -s
?? README

$ git add .

$ git status -s
A README

$ git commit -m 'Initial commit'
```

<p>checks the log message by executing the git log command.</p>

```js
$ git log


commit 19ae20683fc460db7d127cf201a1429523b0e319
Author: gituser <gituser@xyz.com>
Date: Wed Jan 15 07:32:56 2017 +0530

Initial commit

```


<b>Note:</b>
<p>By default, Git pushes only to matching branches: For every branch that exists on the local side, the remote side is updated if a branch with the same name already exists there. In our tutorials, every time we push changes to the <b>origin master</b> branch, use appropriate branch name according to your requirement.</p>

```js

$ git remote add origin gituser@git.server.com:project.git

$ git push origin master


//After execution output looks like this


Counting objects: 3, done.
Writing objects: 100% (3/3), 242 bytes, done.
Total 3 (delta 0), reused 0 (delta 0)
To gituser@git.server.com:project.git
* [new branch]
master −> master

```

## Git - Clone Operation

```js
mkdir gituser_repo

cd gituser_repo/

$ git clone gituser@git.server.com:project.git
```

<p>The above command will produce the following result.</p>

```js
Initialized empty Git repository in /home/gituser/gituser_repo/project/.git/
remote: Counting objects: 3, done.
Receiving objects: 100% (3/3), 241 bytes, done.
remote: Total 3 (delta 0), reused 0 (delta 0)
```

## Git - Perform Changes

Suppose I have added a content in a file called <b>test.js</b>.

```js
$ git status -s

?? test.js  

$ git add string.c


```

<p>Git is showing a question mark before file names. Obviously, these files are not a part of Git, and that is why Git does not know what to do with these files. That is why, Git is showing a question mark before file names.</p>

<p>gituser has added the file to the stash area, git status command will show files present in the staging area.</p>

```js
$ git status -s

A test.js

```

<p>To commit the changes, he used the git commit command followed by <b>–m option</b>. If we omit <b>–m option</b>. Git will open a text editor where we can write multiline commit message.</p>

```js

$ git commit -m 'Implemented function of one testcase'

```

The above commit will produce the  following result

```js
[master cbe1249] Implemented function of one testcase
1 files changed, 24 insertions(+), 0 deletions(-)
create mode 100644 test.js
```

<p>After commit to view log details, he runs the git log command. It will display the information of all the commits with their commit ID, commit author, commit date and <b>SHA-1</b> hash of commit.</p>

## Git - Review Changes

<p>After viewing the commit details, gituser realizes that the string length cannot be negative, that’s why he decides to change the return type of one function.</p>

<p>gituser uses the git log command to view log details.</p>

```js

$ git log

```

<p>The above command will produce the following result.</p>

```js

commit cbe1249b140dad24b2c35b15cc7e26a6f02d2277
Author: gituser <gituser@xyz.com>
Date: Wed Sep 11 08:05:26 2013 +0530

Implemented function of one testcase

```

<p>gituser uses the git show command to view the commit details. The git show command takes SHA-1 commit ID as a parameter.</p>

```js

$ git show cbe1249b140dad24b2c35b15cc7e26a6f02d2277

```
The above command will produce the following ouput

```js

commit cbe1249b140dad24b2c35b15cc7e26a6f02d2277
Author: gituser <gituser@xyz.com>
Date: Wed Sep 11 08:05:26 2013 +0530

Implemented my_strlen function


diff --git a/test.js b/test.js
new file mode 100644
index 0000000..187afb9
--- /dev/null
+++ b/test.js
@@ -0,0 +1,24 @@
+var testCondition = false;
+
+function testCaseExecution()
+{
   +
   testCondition = true;
   +
   +
   if (testCondition){
   +   executeSanityTesting();
   +
   }
}
+

```

gituser adds an <b>else</b> part to the above code, user reviews the code by running the <b>git diff</b> command.

```js

$ git diff

```

The above command will produce the following result.

```js

diff --git a/test.js b/test.js
index 187afb9..7da2992 100644
--- a/test.js
+++ b/test.js
@@ -1,6 +1,6 @@
var testCondition = false;

function testCaseExecution()
{

   testCondition = true;
   
   if (testCondition){
    executeSanityTesting();
  
   -}
   +}else{
     + passTheTestCase();
   +}
}

```

Git diff shows <b>'+'</b> sign before lines, which are newly added and <b>'−'</b> for deleted lines.

## Git - Commit Changes

gituser has already committed the changes and he wants to correct his last commit. In this case, <b>git amend</b> operation will help. The amend operation changes the last commit including your commit message; it creates a new commit ID.

Before amend operation, he checks the commit log.

```js
$  git log
```

The above command will produce the following result.

```js

commit cbe1249b140dad24b2c35b15cc7e26a6f02d2277
Author: gituser <gituser@xyz.com>
Date: Wed Sep 11 08:05:26 2013 +0530

Implemented function of one testcase function

```

gituser commits the new changes with -- amend operation and views the commit log.

```js

$ git status -s
M test.js

$ git add test.c

$ git status -s
M test.js

$ git commit --amend -m 'Added else part for the the same function.'
[master d1e19d3] Added else part for the the same function.
1 files changed, 24 insertions(+), 0 deletions(-)
create mode 100644 test.js

```


## Git - Push Operation

<p>gituser modified his last commit by using the amend operation and he is ready to push the changes. The Push operation stores data permanently to the Git repository. After a successful push operation, other developers can see gituser's changes.
</p>

gituser is ready to push the code.

```js

$ git push origin master

```

The above command will produce the following result:

```js
Counting objects: 4, done.
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 517 bytes, done.
Total 3 (delta 0), reused 0 (delta 0)
To gituser@git.server.com:project.git
19ae206..d1e19d3 master −> master

```

## Fetch Latest Changes
gituser executes the git pull command to synchronize his local repository with the remote one.

```js

$ git pull

```

The above command will produce the following result:

```js

remote: Counting objects: 5, done.
remote: Compressing objects: 100% (3/3), done.
remote: Total 3 (delta 1), reused 0 (delta 0)
Unpacking objects: 100% (3/3), done.
From git.server.com:project
d1e19d3..cea2c00 master −> origin/master
First, rewinding head to replay your work on top of it...
Applying: Added testcasePass function

```

## Git - Stash Operation
<p>Suppose you are implementing a new feature for your product. Your code is in progress and suddenly a customer escalation comes. Because of this, you have to keep aside your new feature work for a few hours. You cannot commit your partial code and also cannot throw away your changes. So you need some temporary space, where you can store your partial changes and later on commit it.</p>

In Git, the <b>stash operation</b> takes your modified tracked files, stages changes, and saves them on a stack of unfinished changes that you can reapply at any time.

```js
$ git status -s

M test.js

```

Now, you want to switch branches for customer escalation, but you don’t want to commit what you’ve been working on yet; so you’ll stash the changes. To push a new stash onto your stack, run the <b>git stash</b> command.

```js

$ git stash
Saved working directory and index state WIP on master: e86f062 Added testcasePass function
HEAD is now at e86f062 Added testcasePass function

```

Now, your working directory is clean and all the changes are saved on a stack. Let us verify it with the git status command.

```js
$ git status -s

Nothing pops up.
```

Now you can safely switch the branch and work elsewhere. We can view a list of stashed changes by using the <b>git stash list</b> command.

```js
$ git stash list
stash@{0}: WIP on master: e86f062 Added testcasePass function
```

Suppose you have resolved the customer escalation and you are back on your new feature looking for your half-done code, just execute the <b>git stash pop</b> command, to remove the changes from the stack and place them in the current working directory.

```js
$ git status -s

Nothing pops up.

$ git stash pop

M test.js
```


## Git - Move Operation
As the name suggests, the move operation moves a directory or a file from one location to another. user decides to move the source code into src directory. The modified directory structure will appear as follows:

```js
$ pwd
/home/user/project

$ ls
README test test.js

$ mkdir src

git mv test.js src/

$ git status -s
R test.js −> src/test.js
```

To make these changes permanent, we have to push the modified directory structure to the remote repository so that other developers can see this.

```js

$ git commit -m "Modified directory structure"

[master 7d9ea97] Modified directory structure
1 files changed, 0 insertions(+), 0 deletions(-)
rename test.js => src/test.js (100%)

$ git push origin master
Counting objects: 4, done.
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 320 bytes, done.
Total 3 (delta 0), reused 0 (delta 0)
To gituser@git.server.com:project.git
e86f062..7d9ea97 master −> master

```

## Git - Delete Operation

```js

$ pwd
/home/gituser/project/src

$ ls
test.js test123.js

$ git log
commit 29af9d45947dc044e33d69b9141d8d2dad37cc62
Author: gituser <gituser123@xyz.com>
Date: Wed Sep 11 10:16:25 2013 +0530

Added a file test123

```

To remove the file <b>git rm</b> can be used.

```js

$ git rm test123.js
rm 'src/test123.js'

[tom@CentOS src]$ git commit -a -m "Removed the file successfully"

[master 5776472] Removed the file successfully
1 files changed, 0 insertions(+), 0 deletions(-)
delete mode 100755 src/test123.js

```

Now ready to push the code.

```js

$ git push origin master

```

## Remove Changes from Staging Area
We have seen that when we perform an add operation, the files move from the local repository to the stating area. If a user accidently modifies a file and adds it into the staging area, he can revert his changes, by using the <b>git checkout</b> command.

In Git, there is one HEAD pointer that always points to the latest commit. If you want to undo a change from the staged area, then you can use the git checkout command, but with the checkout command, you have to provide an additional parameter, i.e., the HEAD pointer. The additional commit pointer parameter instructs the git checkout command to reset the working tree and also to remove the staged changes.

Let us suppose gituser modifies a file from his local repository. If we view the status of this file, it will show that the file was modified but not added into the staging area.

```js
$ pwd
/home/gituser/gituser_repo/project/src

$ git status -s
M test123.js

git add string_operations.c

```

Git status shows that the file is present in the staging area, now revert it by using the git checkout command and view the status of the reverted file.

```js

$ git checkout HEAD -- string_operations.c

$ git status -s

Nothing popups

```

<p style="align:center;">
<img src="https://www.tutorialspoint.com/git/images/before_git_reset.png" alt="Git reset brief"/>
</p>

### Soft
Each branch has a HEAD pointer, which points to the latest commit. If we use Git reset command with --soft option followed by commit ID, then it will reset the HEAD pointer only without destroying anything.

<b>git/refs/heads/master</b> file stores the commit ID of the HEAD pointer. We can verify it by using the <b>git log -1</b> command.

```js
$ cat .git/refs/heads/master

577647211ed44fe2ae479427a0668a4f12ed71a1

```

Now, view the latest commit ID, which will match with the above commit ID.

```js
$ git log -2
```

The above command will produce the following result.

```js

commit 577647211ed44fe2ae479427a0668a4f12ed71a1
Author: gituser <gituser@xyz.com>
Date: Wed Sep 11 10:21:20 2017 +0530

Removed the file successfully


commit 29af9d45947dc044e33d69b9141d8d2dad37cc62
Author: gituser123 <gituser123@xyz.com>
Date: Wed Sep 11 10:16:25 2017 +0530

Added testPass function

```

<b>Let us reset the HEAD pointer.</b>

```js
$ git reset --soft HEAD~
```

<p>Now, we just reset the HEAD pointer back by one position. Let us check the contents of <b>.git/refs/heads/master</b> file.</p>

```js
$ cat .git/refs/heads/master

29af9d45947dc044e33d69b9141d8d2dad37cc62

```

### mixed
Git reset with --mixed option reverts those changes from the staging area that have not been committed yet. It reverts the changes from the staging area only. The actual changes made to the working copy of the file are unaffected. The default Git reset is equivalent to the git reset -- mixed.

### hard
If you use --hard option with the Git reset command, it will clear the staging area; it will reset the HEAD pointer to the latest commit of the specific commit ID and delete the local file changes too.


If Git status is showing that the file is present in the staging area. Now, reset HEAD with -- hard option.

```js
$ git reset --hard 577647211ed44fe2ae479427a0668a4f12ed71a1

HEAD is now at 5776472 Removed the file successfully.
```


## Git - Tag Operation

<p>Tag operation allows giving meaningful names to a specific version in the repository. </p>

Suppose gituser1 and Jerry gituser2 to tag their project code so that they can later access it easily.

### Create Tags
Let us tag the current HEAD by using the <b>git tag</b> command. Tom provides a tag name with -a option and provides a tag message with –m option.

```js
$ pwd
/home/gituser/gituser_repo/project

$ git tag -a 'Release_1_0' -m 'Tagged basic string operation code' HEAD
```

If you want to tag a particular commit, then use the appropriate COMMIT ID instead of the HEAD pointer. Tom uses the following command to push the tag into the remote repository.

```js
$ git push origin tag Release_1_0

Counting objects: 1, done.
Writing objects: 100% (1/1), 183 bytes, done.
Total 1 (delta 0), reused 0 (delta 0)
To gituser@git.server.com:project.git
* [new tag]
Release_1_0 −> Release_1_0

```

### View Tags
gituser1 created tags. Now, gituser2 can view all the available tags by using the Git tag command with –l option.

```js

$ git tag -l

Release_1_0

```

gituser1 uses the Git show command followed by its tag name to view more details about tag.

```js
$ git show Release_1_0

tag Release_1_0
Tagger: gituser1 <gituser1@xyz.com>
Date: Wed Sep 11 13:45:54 2017 +0530

Tagged basic string operation code


commit 577647211ed44fe2ae479427a0668a4f12ed71a1
Author: gituser1 <gituser1@xyz.com>
Date: Wed Sep 11 10:21:20 2017 +0530

Removed the file successfully

diff --git a/src/test123 b/src/test123
deleted file mode 100755
index 654004b..0000000
Binary files a/src/test123 and /dev/null differ

```

### Delete Tags
gituser1 uses the following command to delete tags from the local as well as the remote repository.

```js
$ git tag
Release_1_0

$ git tag -d Release_1_0
Deleted tag 'Release_1_0' (was 0f81ff4)


# Remove tag from remote repository.
$ git push origin :Release_1_0
To gituser@git.server.com:project.git
- [deleted]
Release_1_0

```