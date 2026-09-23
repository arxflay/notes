`git config --list` (show configuration both local and global)
`git config --list --show-origin` (same as previous but shows origin)
`git difftool --tool=<tool>` (use specific tool for diff)
git commit -a (add and commit)
`git log -p <commit>/-<number_of_commits_back>` (output as patch)
`git log --stat` (change summary in each commit)
`git log --graph` (branch graph)
`git log --pretty=format` (output format, could be oneline, full, fuller and custom)
`git log --since` (limit by date)
--no-merge (do not show merge commits)
--author
--before
--amend will add forgotten file or cahnge commit

`git remote -v` (show remote urls)
git remote show remote_name (show information about remote with branches)

git show commit/tag (view changes of specific commit, tag)

git (--local, --global) alias.command_name 'command' (create custom alias for command. Using !command will create custom non git command)
git checkout -b create and switch to branch

HEAD pointer that points branch, more specifically to last commit of that branch

.git/refs - stores data about branches
* heads - branches
* remotes - remotes and their branches
* tags
git branch is just a file with commit hash that it points too
.git/objects - contains compressed data
Git stores everything, e.g creates copy of files in compressed form instead of storing difference like other vcs do. 

`git tag -a` - create annotated tag with name, message and possible signature
`git tag ` - lightweight tag (just a branch)

fast-forward merge - git simply moves pointer. Occurs when last commit from branch we want to merge to is not divergent from branch
three-way (recursive) merge - typical merge, where participants are: last commit before branches were deverged, last commit of branch we want to merge, last commit of branch we want to merge changes from. Result is commit (snaphost) that combines both branches

merge conflicted file section block:
```
<<<<<<HEAD
data = 10
=======
data = 20
>>>>>> merge_from_branch
```
1. first line is merge to branch (HEAD = selected branch)
2. content below is content where conflict occured from merge to view point
3. `======` separator between 
4. content below is content where conflict occured from merge from view point
5. merge from branch
removing `<<<<<< and >>>>>>` in all places in all files and staging them will flag as resolved conflict

git mergetool - select tool fto merge

git branch -v list branches with commit
git branch --move from to: rename branch
git branch -b remote : create and checkout and set upstream
git fetch - update remote tracking information, because git only stores pointers to last commit when lastly communicated with server
git checkout --track - set upstream branch

git rebase - apply changes from other branch without creating merge commit. Final history is linear (change introduced before A will appear before A and vice versa)

git rebase --onto base_branch branch_a diverged_from_a - rebase diverged_from_a as it is base_branch ignoring all commits from branch_a


Hosting:
- to host git repository you don't need gitlab, gitea or etc, git provides enough to host your own git 
1. git protocol - unsafe (doesn't have authentication) which is usable for fast transfer of read only repositories
2. local - any folder that is a bare git repository. Can be created via git clone --bare folder_with_.git_folder repository.git or via git init --bare. All folders must end .git by convention
3. HTTP - dumb and smart variations. Dumb uses hooks and is used only for read only access. Smart is modern variant with authentication and TLS
4. SSH - the easiest option

`git merge --squash from_branch` - will create changeset of all commits from branch without actual merge and commit creation, but staging them

`git diff --check` - check for trailing whitespaces

`git format-patch` - create patches for mail communication

`git push --force-with-leash` - force push but only if someone other doesn't made commit
`git push -u remote branch` - push and track remote
`git add --patch` - git add with preview 
`git am` - apply patches created with git format-patch
`git am -i` - interactive mode, that will try to find all patches in folder
`git am -3` - apply patch but only if patch parent i

1. central workflow - multiple branches in same project. Each member works on it's own branch/es
2. integration-manager workflow - integration of forks
3. dictator-lieutenants workflow - multiplayer integration, contributer -> lieutenants -> dictator -> blessed repository
4. mail patch workflow - old school workflow, when contributor sends bunch of patches 

`git diff branchA...branchB` difference between two branches from common ancestor

topic branch - short lived branch used for implementing feature

merge workflow:
1. Merging straight to master
2. Merging to developer branch and after testing merging features to master. Actually there could be more branches 
3. large-merge workflow -> branches master, next, seen (proposed updates), maintenance. Commits from topics. If commits are safe to merge, they go straight to next. If they are could break some functionality, they are moved to seen and after they are approved, they remerged to master. Maint - for updates for stables releases

`git merge-base branchA branchB` - find commit of common ancestor between branchA and branchB

`git cherry-pick commit` - grab commit from other branch and create this as a new commit in current branch

`git log branchA --not branchB` - show all changes without branchB changes 

rerere (reused recorded resolution) - git config mode that records all pre merge and post merge resolution in cache to later do merge automatically based on similarity with existing pre merge snapshots.

`git describe` - get commit info in format tag-commits_since_tag_added-sha1aabr. If current commit has tag, then describe will return tag (--tags is required for non abbreviated tags)

`git shortlog` - logs only commits names for each autor. Can be shortened with --not

`git archive branch_name` - creates tarball of branch and outputs it to stdout, --format flag to specify format

`git show` - shows object, like blobs (content), trees, tags (diff), branch (diff) commit (diff)

`git ls-remote remote` - check all available branches from remote

`git rev-parse branch/tag` - get hash from branch/tag

`git revlog` - local history of head change for specific branch
`git revlog branch @{date/num}` - state of branch on specific date

`git add -i` - add interactive mode 

`git add --patch` - interactive add dialog for adding portions of files
`git restore --patch` - interactive restore dialog for restoring portions of file

`branchA..branchB` - double dot syntax to make something that is not part of branchA and is part of B

`branchA...branchB` - tripple dot syntax (unique parts for branchA and B)

`git stash -u` - stash even untracked
`git stash --all` stash all
`git stash list` list of stashes
`git stash drop` remove from stash
`git stash apply` apply but not repove
`git stash --keep-index` - stashes files but doesnt remove staged files
`git stash -p` stash only specific parts of files
`git stash apply/pop --index` apply/pop restoring info 
`git stash stash@{}`
about staged files
HEAD^n - n parent of current commit
HEAD~n - n commits behind of current commit

`git log ^branch` equivalent to `git log --not branch`

`git clean` - clean repository
-f = force (required)
--f = remove even submodule
-n = show what will be removed
-x = remove ignored files

`git log -L<func>:<exact_path_to_file>` - logs all commits with patch where specific function was changed

`git log --follow file` - show all commits that changed file 

`git grep` - find pattern in all files in git (faster then typical unix fns find + grep)
--break - add new line after each file
--line-number - add line numbers
-`A<n>` show lines after
-`B<n>` show lines before

`git filter-branch` - dangerous command, that can rewrite entire history 

`git cat-file -p <hash>` prints object (commit, tag, blob)

`git ls-files` show files in current index

`git ls-tree` show files in specific commits/branches

.git/HEAD = pointer to commit
.git/index = are of proposed files to commit (previous file infos are also stored here)
working directory = directory with files

`git reset <commit>` - move head (not change like checkout does) to commit
--soft - moves head, working directory is unchanged and files are still in index
--hard - working directory is indentical to commit moved on
--mixed (default) - similar to soft, but files are not in index (unstaged)