How To Publish Local Changes to a Git Repo

# Publishing Local Changes to a G`it` Repository

---

<aside>
💡 **TLDR;**

From the local repo directory:

1. `$ git pull`
2. `$ git add *`
3. `$ git commit -m "Your commit message here"`
4. `$ git push origin main`
</aside>

### Committing changes

---

From the local repo directory, you can view the changes you’ve made to the repo, add, commit, and push changes.

We’ll use the `eggs` repo as an example.

**NOTE:** I’m pasting the results of running these commands from my local machine. Yours will look different! This guide is intended to walk you through the steps involved in publishing your changes to the remote repository. Each time you make changes, this will look a bit different!

Also, note that it doesn’t matter what conda environment you have activated when running these commands. I’ll do it with my `base` environment activated, but the results would be the same if `eggs` were active.

First, we’ll navigate to our local copy of the repo from our home folder. 

From this directory, use the `git status` command to view the changes we’ve made since the last push (see [note about `git pull`](https://www.notion.so/31242bce46c8497ba2b04467bfc8af1e)):

```bash
(eggs) $ git status

On branch main
Your branch is up to date with 'origin/main'.

Untracked files:
  (use "git add <file>..." to include in what will be committed)
	test.ipynb

nothing added to commit but untracked files present (use "git add" to track)
```

Here, you can see that I’ve created a new file, `test.ipynb`, that hasn’t been published yet.

First, we’ll stage this file for commit by running `git add`:

```bash
(eggs) $ git add *
```

running `git add` followed by a `*` adds all of the modified/created files. If you had made several changes and only wanted to stage/commit certain files, you could run `git add` followed by the file path (e.g. `git add test.ipynb`) to only add specific files to be committed.

Now, if we run `git status`, we can see that this file has been staged for commit (this isn’t necessary; it’s just to show what happens at each step):

```bash
(eggs) $ git status

On branch main
Your branch is up to date with 'origin/main'.

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
	new file:   test.ipynb
```

Next, to **commit** the changes, we’ll use `git commit -m` followed by a short message explaining the modifications or additions made. 

```bash
(eggs) $ git commit -m "Add notebook with code for importing data"

[main 2f0835b] Add notebook with code for importing data
 1 file changed, 1217 insertions(+)
 create mode 100644 test.ipynb
```

**Be sure to edit this commit message to reflect what you’ve done!** This is important for version control, so you can go back to various points in the repo history, and for letting collaborators know what you’ve been up to!

Now, if we run `git status` again, we’ll see that we have 1 commit to push to the remote repository:

```bash
(eggs) $ git status

On branch main
Your branch is ahead of 'origin/main' by 1 commit.
  (use "git push" to publish your local commits)

nothing to commit, working tree clean
```

As `git` tells us above, we can publish these changes using `git push`. At this point, we’ll publish the local changes to the remote repository on GitHub, which allows others with access to the repository to see the changes we’ve made. Up until now, all of the edits **only exist locally.** After pushing the changes, they are synced on GitHub.

Publish changes by running `git push origin` followed by the name of the branch you want to make changes to. For the sake of simplicity, I won’t go into branches here, as our repo only has one branch, `main`, and we likely won’t create additional branches to worry about in the near future...

```bash
(eggs) $ git push origin main

Enumerating objects: 4, done.
Counting objects: 100% (4/4), done.
Delta compression using up to 10 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 5.75 KiB | 5.75 MiB/s, done.
Total 3 (delta 1), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
To git@github.com:HEAL-KGS/eggs.git
   f650021..2f0835b  main -> main
```

Now all the changes we’ve made have been published. If we go to the repo on GitHub in the browser, we’ll be able to see the commits we made.

<aside>
💡 Note that it’s generally a good idea to run `$ git pull` before adding any changes. This step updates your local copy of the repo with any changes that have been made to the remote repository (i.e. changes that others have made).

For example, everything I’ve done up to this point has been from my local machine. I can now navigate to my local copy of the repo, and see the new file.

-If no changes have been made, great, there’s no harm in running this command:

-However, if you attempt to push your changes to the remote repo without pulling first, `git` will yell at you. 

Sometimes pulling gets tricky if you’ve made changes to a file locally and someone else has edited it and published their changes already. But we’ll not worry about that for now.

</aside>