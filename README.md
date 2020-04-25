# GitGames
Awesome git games that can be a fun way to learn git

1. https://learngitbranching.js.org/
2. https://github.com/git-game/git-game
3. https://github.com/git-game/git-game-v2
4. https://github.com/Gazler/githug

### Solutions to Git-Game-v1
| Level | Solution |
|:-----:|:--------:|
| 1 | git checkout 6402 |
| 2 | git checkout bug |
| 3 | git blame cool.cpp > git checkout LinusTorvalds2014 |
| 4 | vim .gitignore |
| 5 | git checkout tree |
| 6 | /outputclue.sh nextclue_input.cpp |
| 7 | git fetch origin/code4life <br>git merge origin/code4life <br>./outputclue.sh nextclue_input.cpp <br>git checkout mouse |
| 8 | git diff mouse bug -- remember <br>git checkout Henry |
| 9 | git checkout origin/Henry |
| 10 | git remote add remote https://github.com/drami025/git-game.git <br>git pull remote master |

### Solution to Git-Game-v2
| Level | Solution |
|:-----:|:--------:|
| 1 | git ls-files | xargs wc -l <br>git checkout 6861 |
| 2 | git log <br>git show 16a28 <br>git checkout snowden |
| 3 | git shortlog <br>git checkout anon |
| 4 | git describe <br>git checkout return <br>git checkout preety |
| 5 | git log --pretty=format:"%t  %s <br>git checkout SIGPOLL <br>git log --pretty=format: ''tree hash: %t --> subject: %s'' |
| 6 | git submodule init <br>git submodule update --init --recursive <br>cd Java <br>cd .. <br>git checkout history <br>git submodule init #then  git submodule update |
| 7 | git log -p --full-diff (can use git grep and git rev-list) <br>git checkout cherry <br>git grep "@hint" $(git rev-list history) |
| 8 | git checkout arachnid <br>git checkout HEAD\~4 <br>git checkout insect <br>git checkout HEAD\~3 <br>git checkout cherry <br>git cherry-pick 180fc7bb b441b5bb <br>cat consonents.txt && vowels.txt <br>git checkout lighthouse <br>git cherry-pick arachnid\~4 insect\~3 |
| 9 | git bisect start <br>git log --pretty=oneline --reverse | head -1 <br>git bisect good 394217 <br>git log --preety=oneline --reverse | tail -1 <br>git bisect bad 662efa <br>cat twinkle.txt <br>git bisect bad / git bisect good <br>ls <br>cat message <br>git checkout root |

### Solutions to Git Hug
**Getting started**
```bash
# https://github.com/Gazler/githug

# install ruby and check installation
ruby -v / ruby --version

# installing
gem install githug

# running
githug

# seeing hint
githug hint
```

**Levels**

	1. A new directory, `git_hug`, has been created; initialize an empty repository in it.
		git init
		
	2. Set up your git name and email, this is important so that your commits can be identified.
		git config user.name "deepak"
		git config user.email "deepak.sood@zenatix.com"
		
	3. There is a file in your folder called `README`, you should add it to your staging area
		git add README
		
	4. The `README` file has been added to your staging area, now commit it.
		git commit -m "initial commit"
		
	5. Clone the repository at https://github.com/Gazler/cloneme.
		git clone https://github.com/Gazler/cloneme
		
	6. Clone the repository at https://github.com/Gazler/cloneme to `my_cloned_repo`
		git clone https://github.com/Gazler/cloneme my_cloned_repo
		
	7. The text editor 'vim' creates files ending in `.swp` (swap files) for all files that are currently open.  We don't want them creeping into the repository.  Make this repository ignore those swap files which are ending in `.swp`.
		vim .gitignore
		add *.swp to file
		:wq to save
		
	8. Notice a few files with the '.a' extension.  We want git to ignore all but the 'lib.a' file.
		vim .gitignore
		add *.a and !lib.a to file

	9. There are some files in this repository, one of the files is untracked, which file is it?
		git status
		Enter - database.yml
		
	10. There are some files in this repository, how many of the files will be committed?
		git status
		Enter - 2
		
	11. A file has been removed from the working tree, however the file was not removed from the repository.  Find out what this file was and remove it.
		git status
		git rm deleteme.rb
		
	12. A file has accidentally been added to your staging area, find out which file and remove it from the staging area.  *NOTE* Do not remove the file from the file system, only from git.
		git status
		git rm --cached deleteme.rb
		
	13. You've made some changes and want to work on them later. You should save them, but don't commit them.
		git stash
		
	14. We have a file called `oldfile.txt`. We want to rename it to `newfile.txt` and stage this change. (We do not want to use linux mv command, since it deletes the old file and create new file with new name and stage that to git)
		git mv oldfile.txt newfile.txt
		
	15. You added some files to your repository, but now realize that your project needs to be restructured.  Make a new folder named `src` and using Git move all of the .html files into this folder.
		mkdir src
		git mv *.html src
		
	16. You will be asked for the hash of most recent commit.  You will need to investigate the logs of the repository for this.
		git log
		copy the hash
		1bc8af6976b6fd491c5008c0268c6adedecd54d4

	17. We have a git repo and we want to tag the current commit with `new_tag`.
		https://git-scm.com/book/en/v2/Git-Basics-Tagging
		git tag -a new_tag -m 'tag v1'
		git tag (to verify the tag)
		git log (to check the tag)
		
	18. There are tags in the repository that aren't pushed into remote repository. Push them now.
		git log
		git push origin tag_to_be_pushed (push the passed tag)
		git push --tags (push all tags, not recommended)
		
	19. The `README` file has been committed, but it looks like the file `forgotten_file.rb` was missing from the commit.  Add the file and amend your previous commit to include it.
		git status
		git add forgotten_file.rb
		git commit --amend -m "commit message"
		
	20. Commit your changes with the future date (e.g. tomorrow).
		git commit -m "message" --date "Oct 11 2018"
		git commit -m "message" --date "Tue Apr 28 23:00:00 2015 +0300"
		
	21. There are two files to be committed.  The goal was to add each file as a separate commit, however both were added by accident.  Unstage the file `to_commit_second.rb` using the reset command (don't commit anything).
		git rm --cached to_commit_second.rb (This removes a file from being tracked)
		git reset HEAD to_commit_second.rb (This continues to keep tracking changes to the file, but will place it back into the unstaged area)
		
	22. You committed too soon. Now you want to undo the last commit, while keeping the index.
		git reset --soft HEAD~
		
	23. A file has been modified, but you don't want to keep the modification.  Checkout the `config.rb` file from the last commit.
		git checkout config.rb
		
	24. This project has a remote repository.  Identify it.
		git remote -v
		sol - my_remote_repo
		
	25. The remote repositories have a url associated to them.  Please enter the url of remote_location.
		git remote -v
		sol - https://github.com/githug/not_a_repo
		
	26. You need to pull changes from your origin repository.
		git remote -v
		git pull origin master
		
	27. Add a remote repository called `origin` with the url https://github.com/githug/githug
		git remote add origin https://github.com/githug/githug
		
	28. Your local master branch has diverged from the remote origin/master branch. Rebase your commit onto origin/master and push it to remote.
		git pull --rebase origin master
		git push origin master
		
	29. There have been modifications to the `app.rb` file since your last commit.  Find out which line has changed.
		git diff app.rb (shows +3 and -3 lines before and after the actual change)
		git diff -U0 (set the context to current line)
		git blame
		sol - 26
		
	30. Someone has put a password inside the file `config.rb` find out who it was.
		git blame config.rb
		sol - Spider Man
		
	31. You want to work on a piece of code that has the potential to break things, create the branch test_code.
		git branch test_code
		
	32. Create and switch to a new branch called my_branch.  You will need to create a branch like you did in the previous level.
		git branch my_branch
		git checkout my_branch, or
		git checkout -b my_branch

	33. You need to fix a bug in the version 1.2 of your app. Checkout the tag `v1.2`.
		git checkout v1.2
		
	34. You need to fix a bug in the version 1.2 of your app. Checkout the tag `v1.2` (Note: There is also a branch named `v1.2`).
		git checkout tags/v1.2
		
	35. You forgot to branch at the previous commit and made a commit on top of it. Create branch test_branch at the commit before the last.
		git log --graph
		git checkout HEAD~
		git branch test_branch
		
	36. You have created too many branches for your project. There is an old branch in your repo called 'delete_me', you should delete it.
		git branch
		git branch -d delete_me
		
	37. You've made some changes to a local branch and want to share it, but aren't yet ready to merge it with the 'master' branch.  Push only 'test_branch' to the remote repository
		git remote -v
		git branch
		git push origin test_branch

	38. We have a file in the branch 'feature'; Let's merge it to the master branch.
		git merge feature
		
	39. Looks like a new branch was pushed into our remote repository. Get the changes without merging them with the local repository
		git fetch
		
	40. We are using a git rebase workflow and the feature branch is ready to go into master. Let's rebase the feature branch onto our master branch.
		git checkout feature
		git rebase master
		git merge feature
		
	41. You have created your branch from `wrong_branch` and already made some commits, and you realise that you needed to create your branch from `master`. Rebase your commits onto `master` branch so that you don't have `wrong_branch` commits.
		git log
		git rebase --onto master wrong_branch readme-update
		
	42. Optimise how your repository is packaged ensuring that redundant packs are removed.
		A pack is a collection of objects, individually compressed, with delta compression applied, stored in a single file, with an associated index file.
		
		git repack -d
		Ref - https://git-scm.com/docs/git-repack
		
	43. Your new feature isn't worth the time and you're going to delete it. But it has one commit that fills in `README` file, and you want this commit to be on the master as well.
		git log
		git branch
		git checkout new-feature
		git log
		copy the hash for commit Filled in Readme.md with proper input
		git cherry-pick ca32a6dac7b6f97975edbe19a4296c2ee7682f68
		
	44. Your project's deadline approaches, you should evaluate how many TODOs are left in your code
		git grep -n "TODO" (n for printing line numbers)
		git grep --count "TODO"
		Ref - https://git-scm.com/docs/git-grep
		sol - 4
		
	45. Correct the typo in the message of your first (non-root) commit.
		git log
		git rebase -i HEAD~2
		Change the First commit to edit
		git log
		git commit --amend -m "First commit"
		git rebase --continue
		git log
		
	46. You have committed several times but would like all those changes to be one commit.
		git log
		git rebase -i HEAD~4
		Change the commits to squash
		git log
		
	47. Merge all commits from the long-feature-branch as a single commit.
		git log --all --decorate --graph --oneline
		git merge --squash long-feature-branch
		git commit
		
	48. You have committed several times but in the wrong order. Please reorder your commits.
		git log --all --decorate --graph --oneline
		git rebase -i HEAD~3
		Change order of the commit
		git log --all --decorate --graph --oneline
		
	49. A bug was introduced somewhere along the way.  You know that running `ruby prog.rb 5` should output 15.  You can also run `make test`.  What are the first 7 chars of the hash of the commit that introduced the bug.
		git bisect start
		make test
		git bisect bad
		git bisect next
		make test
		git bisect good
		make test
		git bisect good
		git bisect reset
		sol - 18ed2ac
		
	50. You've made changes within a single file that belong to two different features, but neither of the changes are yet staged. Stage only the changes belonging to the first feature.
		git add -p feature.rb
		Stage this hunk [y,n,q,a,d,e,?]? e
		Comment the second line
		
	51. You have been working on a branch but got distracted by a major issue and forgot the name of it. Switch back to that branch.
		git branch
		git checkout solve_world_hunger
		
	52. You have committed several times but want to undo the middle commit. All commits have been pushed, so you can't change existing history.
		git log 
		git revert HEAD~1
		
	53. You decided to delete your latest commit by running `git reset --hard HEAD^`.  (Not a smart thing to do.)  You then change your mind, and want that commit back.  Restore the deleted commit.
		git reflog
		git cherry-pick 70f98e1
		
	54. You need to merge mybranch into the current branch (master). But there may be some incorrect changes in mybranch which may cause conflicts. Solve any merge-conflicts you come across and finish the merge.
		git branch
		git merge mybranch
		vim poem.txt
		git add poem.txt
		git commit -m "resolved conflict"
		
	55. You want to include the files from the following repo: `https://github.com/jackmaney/githug-include-me` into a the folder `./githug-include-me`. Do this without manually cloning the repo or copying the files from the repo into this repo.
    git submodule add https://github.com/jackmaney/githug-include-me