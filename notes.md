# Version Control

"Is a system that records changes to a file or set of files over time so that you can recall specific versions later."
A.K.A Source Control Management

# Git
"Git is a free and open source distributed version control system designed to handle everything from small to very large projects with speed and efficiency."

- Popular version control
- Born with Linux project <3
- Command line application :o

## Centralised vs. Distributed
### CVS, Subversion

- Repo resides on some **central server**
- Client only has **one version** of trunk or branch

### Git, Mercurial

- The full repo resides locally
- Contains full history
- Server is (almost) not involved
    > - Commit often & offline
    > - Work anywhere!
- Easy backups

## Git workflow

working directory -> git add -> staging area -> git commit -> repository

## Git commands
Overview:
    > git init
    > git status
    > git add .
    > git branch [branch-name]
    > git checkout [branch-name]
    > git commit -m 'message'
    > git merge [branch-name]
    > git log [-a]

### git init
Run this to initialize a git repository in your folder. Only run once.

### git status
This is your friend. 
Run it whenever you feel like you don't know what you're doing.
Or just run it for fun.

### git add .
Add untracked files to staging area (begin tracking).
Add a modified tracked file to staging area.

$ git add file.txt
$ git add .

Files can be in one of the four following stages:
* Untracked
* Modified (working directory)
* Modified (staging area)
* Committed

### git commit
The all-powerful commit. Once you're ready and the files are in the staging area (via git add), congratulations! You are ready to commit!

$ git commit

This will open your default text editor (in the terminal). On Unix (Mac & Linux) and Windows Git Bash, that would be Vim (which is super hard if you have never used it). If you're over-eager and ran it already and are now stuck in Vim (a super cool but super hard text-editor in the terminal), press Esc, then type :x (in the bottom left corner you should see your typing), then Enter.

All commit messages must be accompanied from a commit message. "Like miniskirts, short enough to maintain interest, but long enough to cover the subject." Try to make these commit messages meaninful to you.

Shortcut to include the message in the command:
$ git commit -m "Your commit message here"

Shortcut to add and commit in one command:
$ git commit -am "Your commit message here"

### .gitignore
Sometimes, you will want Git to ignore some files in your working directory from tracking (you normally don't want to commit your database configuration files or files that include passwords). For this purpose, you can create in the root directory a file called .gitignore. On each new line, put the name of the file(s) or folder(s) you want Git to ignore. Some great examples here

It should look like this:

app/config.rb
app/database.rb
verysensitivefile.cpp
ignorethisfolder/
'# .gitignore files accept wildcards:
'# ignore everything in this folder that ends in .jpg: 
folder/*.jpg

'Ignrore all "uploads" file but config.txt'
!uploads/config.txt

### git diff
This command will tell you what changed from state to another.

$ git diff # tells you everything that's different between your HEAD commit and your current working directory
$ git diff file1 file2 # difference between file1 (old) and file2 (new)
$ git diff commitHash1 commitHash2 # difference between one commit and another (all files)
$ git diff commitHash1 commitHash2 file.c # same file, two different commits

### git rm
Remove files from the working tree and from the index

### git log
Keys to move.
j: forward, k: back

Show a timeline of each commit in oneline.
git log --oneline --graph --all

Show which files where changed in each commit.
git log --stat

### git checkout
Changes your location to a past moment referencing the commit hash.
git checkout [hash]

## Branching
Create a branch.
git branch [branch-name]

Show all branches.
git branch

Move to branch testbranch.
git checkout testbranch

### Merging to master.
- If it is your own project:
git checkout master
git merge testbranch
git branch -d testbranch

- If it is a group project:


