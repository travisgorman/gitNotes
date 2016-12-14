#Branching and Merging

### `git clone`

		git clone <URL-of-the-remote-repository> <optional-name>

* downloads the entire repository into a new directory
* adds the `origin` remote, pointing it to the clone URL

		git remote -v

* Checks out initial branch (most likely `master`), and sets the HEAD.

___

### `git branch`

		git branch <branch-name>
create branch from master
		git checkout <branch-name>

* commit to new branch
* commits to new branch won't be available on `master`
___


from `master` branch (the branch you want to **merge into**)

		git merge <branch-to-merge-into-master>

### Fast-Forward Merge
![fast-forward merge]()
Merging commits from one branch into another branch with nothing new on it. It is the same as it was when the branch was created, so has no problem merging.  

		git branch -d <branch-to-delete>

--> deletes a branch you no longer need after it's been merged

		git checkout -b <new-branch>

--> creates a new branch and switches to it 

* Make a few commits on new branch

While you're working on your branch, suddenly...

* Changes must be made to the `master` branch, so you switch to `master` and commit some new changes. 

Now that you're back on the `master` branch, you need sync your local repository with the remote repository.

		git pull 

--> to make sure you have the most current version, and fix whatever you need to on the `master` branch.

* Switch back to your other branch and finish your feature

Now you're ready to merge your branch with `master` 

		git checkout master
		git merge <new-branch>

Now you're trying to merge a branch with one that has changes on it.

Git will prompt for more specific commit messages (Atom, or Vi)
Providing a default of 

		Merge branch <new-branch>

You can write something more specific, or accept the default.

		:wq

To save and go back to command line

### Recursive Merge
Git can't fast forward since changes were made in both branches. It recursively merges the two, and creates a commit in the log, merging them together.

___

# Colaboration Basics

### `git pull`
Syncs our **local** repository with the **remote** one `git fetch`
Locally merges our `origin/master` branch with `master`. It's the same as
		
		git merge origin/master


### merge commit
The prompt that pops up when trying to merge to master — forces a recursive merge.
Now we need to push to origin master with `git push`. Making our local and origin/master the same

	
### merge conflicts

![merge conflict]()

This needs to be edited manually. After fixing the conflict

		git commit -a

to perform a **merge commit**. You'll be taken to an editor and will need to save and confirm changes.
Finally, 

		git push

to sync with the remote repository

___

# Remote Branches & Tags






















































































