

## Use `git` on Raspberry Pi with GitHub

***Here's a procedure for using `git` on your RPi to interface with GitHub repositories. We use the `PiPyMailer` repo as an example. PiPyMailer is designed to run on a Raspberry Pi, and so it makes sense to source it there.*** 

1. @github.com, copy the URL of the repo to be cloned on RPi:
    `https://github.com/seamusdemora/PiPyMailer.git` 

2. in a terminal session to RPi, enter this: 
    `git clone https://github.com/seamusdemora/PiPyMailer.git`

  this should download the repo into a folder named `PiPyMailer` on RPi

3. `cd ./PiPyMailer`
   Alternatively, you can execute most `git` commands from *outside* the folder housing the repo by using the `-C` option; for example, to get `status` for the git repo PiPyMailer from another location: 
```bash
  git -C /path/to/PiPyMailer status
```
5. make your changes, test your code. when code is verified, proceed w/ next step
6. `git status` to review additions & changes; e.g.
    On branch master
    Your branch is up-to-date with 'origin/master'.
    Changes not staged for commit:
    	(use "git add <file>..." to update what will be committed)
    	(use "git checkout -- <file>..." to discard changes in working directory)

  	modified:   testmail2.py

  Untracked files:
  	(use "git add <file>..." to include in what will be committed)

  	change.crontab.txt
  	change.profile.txt

6. move modified file(s) to staging area:
    `git add testmail2.py`

7. move added file(s) to staging area
    `git add change.crontab.txt change.profile.txt` 

8. verify all required files are in staging area:
    `git status`

9. commit changes to the branch from which the local repo was cloned:
    `git commit`

10. edit the offered "COMMIT_EDITMSG" file

  1. NOTE 1: `git config --global content.editor "nano -w"` (wait for me to finish!)
  2. NOTE 2: you *must* add a non-commented line to the commit message

11. now that changes are "committed", they must be "pushed" to GitHub: 
      `git push origin master`

   If all goes well, you'll be prompted for GitHub userid & pswd, and changes will
   appear in the correct repo! 

14. If you *break sync* in your GitHub repo, [read this](https://github.com/seamusdemora/seamusdemora.github.io/blob/master/MacStuff.md#15-how-to-recover-a-bodged-git-repository). You can *break sync* in a local repo if you have multiple copies (e.g. on more than one local machine), and allow uncommitted changes to accumulate on two or more of these machines. Be careful - this can be **very messy**!  

<hr>

### REFERENCES:

* [Getting Started with Git](https://www.taniarascia.com/getting-started-with-git/) 
* [Q&A: How to move a git repository into another directory and make that directory a git repository?](https://stackoverflow.com/questions/19097259/how-to-move-a-git-repository-into-another-directory-and-make-that-directory-a-gi) For shuffling things around! 




