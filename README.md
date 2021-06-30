# LittleVersionControl
lvc is a minimalist verion control tool (storing differences as patches)

## Why ?
lvc is simpler than git or svn, it works locally, simply stores your old versions as patches. It is meant to be a small tool to use whenever you write a small script...

## Dependencies
These should be installed by default on any system:
 - diff (from difftools)
 - patch
 - less
Common on most system:
 - python3

Optional:
 - batcat (Better than less to display patch files)
 
 ## Installation
 To install it on any linux machine:
  - Download the file called lvc in this repository
  - Make it executable: `chmod a+x ./lvc`
  - Move it to /usr/bin/lvc: `sudo mv ./lvc /usr/bin/`
 
 ## Usage
 ```bash
lvc init # Create a repository in the current directory
lvc log # Print the history
lvc commit <File/Directory> [<File/Directory> ...] # Commit the changes made to these files/directories, use directories to group commits together
lvc discard # Discard the current changes on the work directory and go back to the last commited change (aka master)
lvc status # List the differences between the work directory and master
lvc revert # Revert the work directory to a commit (listed by 'log')
 ```
## How does it work ?
It is meant to be simple and stores previous version of your work in clear .patch files
When 'init' is used it creates hiden directories (.master .history)
.master contains the last version you commited (called master)
.history contains the patches you can revert to if you are not happy with your master
Once you modified one or many files you can 'commit' then to the master (you will be
prompt to review the changes and asked for confirmation).
If you no longer want your local changes you can 'discard' them.
You can use 'log' to list all the commits and the tags (description) you gave them
