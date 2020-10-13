# Revisions in the Cloud
---

## Version Control
Version Control Systems(VCS) are systems that allow developers to:
1. Track modifications to files
1. Compare changes made to files
1. Revert files or projects to previous versions
1. Easily rectify mistakes made in modifications

In the past, programmers utilized Local Version Control(LVC), which consisted of a database on a single computer that kept a record of chages to files. This approach was not conducive to collaboration however. The use of Centralized Version Control Systems(CVCS) emerged to not only make the collaboration process more viable but also to streamlined it as well. The database of changes to files was kept on a server which individual programmers could access. The issue with CVCS was that it was vulnerable. If the server went down or suffered corruption, programmers could not collaborate with no back up files data would be lost. CVCS were eventually replaced by Distributed Version Control Systems(DVCS) in order to address this vulnerability. To prevent catastrophic data losses DVCS allow the creation of mirrored repositories by clients. Git is one such DVCS. Since 2005, Git has become one of the most utilized VCS in the world.

# Git

Some of the benefits of Git are:
- Stores data in a file system in a series of snapshots
- Relies on local operations that allows project work to continue when not online
- Tracks every change made to files or directories
- Detects file corruption or loss of information
- Greatly minimizes the possibility of irreversible damage to files and data loss

## States

Files in Git exist in three main states:
- ### Committed
  - Data is securely stored in a local database.
- ### Modified
  - File has been changed but not committed to the database.
- ### Staged
  - Flagged a file’s changed version to be committed in the next snapshot.
  
### Initial Configuration

After installing Git, settings for identity and text editors should be configured using `$ git config`.

Setting the user name to 'John Doe' would be accomplished by:
```
$ git config --global user.name "John Doe"
```

Setting the email address to 'email@email.com' is done by:
```
$ git config --global user.email "email@email.com"
```

Setting the text editor to emacs...
```
$ git config --global core.editor emacs
```

The use of *--global* in these commands applies the settings accross the whole system.
  
## Useful Git Commands in the Terminal

| #### Command | #### Description |
| --- | --- |
| `$ git config --list` | Checks the current settings |
| `$ git clone https://github.com/test` | Creates directory named test with copies of all files in the project |
|  | Also checks out a copy of the newest version for editing. |
| `$ git add filename` | File filename is tracked and staged for committing |
| `$ git commit -m "note about changes made` | Commits the changes and records what you did within the commit message |
| `$ git push origin main` | Pushes changes from the local “main” branch to the remote repository |
| `$ git status` | Shows information regarding changes to be committed |


[Back to Main](README.md)
