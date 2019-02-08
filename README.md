# Git ignoring already tracked files

## Question
Another question inspired from /r/git.
>Help! Git tells me files are modified but I've added those files to my .gitignore yet the messages persist. How do I stop this behavior once and for all?

## Explanation
Regardless of .gitignore, Git tracks files indefinitely once committed to the repository. While this can be frustrating, within a few seconds we can right the ship and ignore those files (or folders) once and for all.

## Solution
To follow along, pause the video and clone this repository (https://github.com/dvcsnow/forgetme). Otherwise hang tight to watch and learn. 

In our previously staged repository, we have a folder that contains files that we actually need to ignore like they never existed. The secret is to use the `git rm` command to tell Git "nevermind!".

1. `git status` to verify Working Directory is clean.
1. `git rm -r --cached /path/to/folder` to forget the stuff.
   1. `-r` means "Allow recursive removal when a leading directory name is given."
   2. `--cached` means "Use this option to unstage and remove paths only from the index. Working tree files, whether modified or not, will be left alone." 
2. `git status` to see what has changed.
3. `git commit -m "removed the folder"` to commit.
4. `git status` to see Git recognizes untracked files.
5. Update `.gitignore` to include the folder path.
6. `git status` to show Git now ignores the files.

Thanks for watching.