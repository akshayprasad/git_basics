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