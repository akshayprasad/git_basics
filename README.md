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