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


from `master` 

		git merge <branch-to-merge-into-master>

### Fast-Forward Merge
![fast-forward merge]()
Merging commits from one branch into another branch with nothing new on it. It is the same as it was when the branch was created, so has no problem merging.  

		git branch -d <branch-to-delete>

deletes a branch you no longer need after it's been merged

		git checkout -b <new-branch>

creates a new branch and switches to it 

* Make a few commits on new branch

While you're working on your branch, suddenly...

* Changes must be made to the `master` branch, switch to `master` and commit some new changes. 

when going back to the master, `git pull` to make sure you have the most current version, and fix whatever you need to on the `master` branch.

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


