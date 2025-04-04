# git-group-tutorial
The purpose of this tutorial is to learn and apply git commands needed to collaborate on a team project.

Goal:
Familiarize students with essential GitHub operations and group collaboration workflow with GitHub, including forking, cloning, branching, committing, resolving conflicts, pull requests, merging, and deploying on GitHub Pages.
Using GitHub via Windows/Unix commands
Using commands is efficient however it’s not as beginner friendly as using the GitHub app. This document contains instructions on how to complete this assignment using commands in either the cmd or vs code’s terminal.
Commands to know:
Basic:
1.	Cd (Change Directory) – This command is used to enter or exit a directory.
a.	For example, if you are on “C:\Users\HP\OneDrive” using `cd Desktop` brings you to “C:\Users\HP\OneDrive\Desktop”
b.	To exit “C:\Users\HP\OneDrive\Desktop” you must do `cd ..` which brings you to “C:\Users\HP\OneDrive”
2.	Git clone – This command clones all the files on a repository to a chosen directory. A folder is created with a sub folder marked as .git, which is what links your directory to the repository.
a.	`git clone <repository link>`
3.	Git init – This command is similar to `git clone` however instead of being used to connect to an existing repository, you use this command to connect to a new repository.
a.	`git init`
4.	Git add – This command is used to add new files or updated files to the staging area.
a.	`Git add <file>` or `git add .` to add every file that’s been modified.
b.	Run this command before doing commit or push.
c.	Why you would use it: Before committing changes, you need to stage them. This command allows you to select which changes you want to include in the next commit.
d.	This doesn’t update the repository or allow you to push.
5.	Git commit – This command is used to lock in the changes you have made to the stream, basically saying “yes these are ready to be added publicly to the repository”.
a.	Command: `git commit -m "Your commit message"`
b.	Purpose: Commits create a snapshot of the project at a specific point in time with a descriptive comment of what was done.
c.	Why: Commits create a history of changes, making it easier to track the evolution of the project. Each commit is identified by a unique hash, and you can revert to any commit in the history. Commit messages also serve as documentation, helping collaborators understand the purpose of each change.
6.	Git push – This command makes all the changes you have made to the repository public for everyone with access to the repository.
a.	Command: `git push origin <branch-name>`
b.	You can link your repository to a specific branch by running `git push -u origin <branch-name>` This allows you to simply run `git push` and changes will be automatically added to that branch.
Intermediate:
7.	Git fetch
a.	Purpose: Fetching is a non-destructive operation, it updates from a repository allowing you to see what changes are available without automatically merging them into your current working branch which otherwise could cause conflicts.
b.	Command: `git fetch <repository link>`
c.	After fetching, you can inspect the changes using commands like `git log` or `git diff`. It gives you the opportunity to decide whether to merge the changes into your local branch or not.
8.	Git pull – quickly synchronizes your local files with the repository, however it might lead to conflicts that need to be resolved.
a.	Purpose: Pulling updates from a remote repository is a combination of fetching and merging. It fetches changes and automatically merges them into your current working branch.
b.	Command: `git pull <repository link> <branch>` or `git pull` (if already connected)
9.	Git rebase - In very simple terms allows you to pull changes and merge them with your files without having to do a merge/pull request.
a.	This works by resolving conflicts (if any) and then your local commits are applied on top of the fetched changes.
b.	This is practical because it makes your commit history uncluttered from merge commits.
10.	Git Stash – Saves changes without publishing them. Each stash is added to a list of stashes which can be accessed with various commands. Useful when wanting to update a branch that has work in progress that isn’t ready to be committed or if you want to switch branches to work on something else with unfinished work on the current branch.
a.	Git stash list – Lists all the stashes.
b.	Git stash – Stashes with a default stash message
c.	Git stash push -m “comment” – Stashes with a custom message, useful if you use stashes often and want to know what each was for.
d.	Git stash apply – Applies the most recent stash but keeps it in the list.
i.	Git stash apply stash@[#] – Applies a specified stash but keeps it in the list.
e.	Git stash pop – Applies the most recent stash but removes it from the list.
i.	Git stash pop stash@[#] – Applies and removes a specified stash. 
f.	Git stash drop – Drops the most recent stash without applying it.
i.	Git stash drop stash@[#] – Drops a specified stash without applying it.
g.	Git stash clear – Clears the list of all stashes.
