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
2. `git rm -r --cached crap` to forget the stuff and stage the removal.
   1. `git help rm` for flag explanations.
3. `git status` to see what has changed.
4. `git commit -m "removed the folder"` to commit.
5. `git status` to see Git recognizes untracked files.
6. Update `.gitignore` to include the folder path.
7. `git status` to show Git now ignores the files.

Thanks for watching.