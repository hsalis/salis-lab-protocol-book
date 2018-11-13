# Git

### What is Git?

"By far, the most widely used modern version control system in the world today is Git. Git is a mature, actively maintained `open-source` project originally developed in 2005 by Linus Torvalds, the famous creator of the Linux operating system kernel. A staggering number of software projects rely on Git for version control, including commercial projects as well as open-source."

...OK what? This is the introduction paragraph on a [What is Git](https://www.atlassian.com/git/tutorials/what-is-git) resource page, and admittedly it's not very informative. The first time I read about version control, I was overwhelmed. Computer scientists are notorious for using technical jargon - and the world of Git is no exception. There are dozens of [content-rich websites](git.md#resources) describing "how to Git" at various skill levels, and while they contain everything you need to know, they tend to poorly describe the usage that you might use in your own workday. I find that I am frequently describing git basics to new students in our lab, and while I recommend you go and read up on version control and Git on your own, this guide is designed to teach basic usage.

### Why do we use Git?

For development we need a way to: 1. Maintain a history of development. 2. Collaborate on projects. 3. Use resources developed by other people. 4. Share our code with the world.

### Version control

The above list is exactly what Git does for us. The first two items describe what is called `version control`. Version control allows us to track changes in computer files and coordinate work on those files among multiple people. With version control you can see how your changes affect your project before "committing" to them \(we'll discuss `commit` as a command in a bit\). If you notice that something broke in your project that worked before, you can simply roll back one revision at a time until you find the revision that caused the regression. Version control also allows us to concurrently edit files. Git manages differences in files \(`diff`, another command\), and won't allow you to overwrite changes to files that you teammates have made, without resolving those differences first. If you try, Git will tell you there is a `merge conflict` that must be resolved.

### Repositories

Git manages a directory of code for a project, we call this a `repository`. Every collaborator on a project copies the repository to their machine \(`clone`\) and can make changes locally. Every Git directory on every computer is a full-fledged repository with complete history and full version tracking abilities, independent of network access or a central server. We will see in the Git commands section how changes to your local repo can get "pushed" \(`push`\) and how changes made by the team can be "pulled" \(`pull`\) from the server version of shared repository.

Our group uses `GitHub`, a Git repository hosting service, to host our shared repository, [Private-Code](https://github.com/hsalis/Private-Code). This repository hosts the core package that our group develops, the [DNA Compiler](../dna-compiler/). `GitHub` offers two types of repositories: public and private. `Private-Code` is a private respository, meaning only collaborators can see the code.

Public repositories are great when you want to share your code with the world to use. Code that is public is called `open-source`. My first project was to develop a model test system for sequence-function gene expression models. We decided to open-source the project so that anyone interested in model development can use it. Check it out at [test-sfm](https://github.com/reisalex/test-sfm). If you're looking for a quick guide on how to create and build your own repository go to [Setting up a repo](../dev/setting-up-a-repo.md).

[![](../../.gitbook/assets/github.png)](https://github.com/)

GitHub has a mascot called Octocat, a cat with five tentacles and a human-like face.

### Salis Lab Private-Code

Navigate to [Private-Code](https://github.com/hsalis/Private-Code). If you can't, that means you need to get Dr. Salis to add you as a collaborator. Email him now! You'll need to set up a username and password for GitHub.

## Git commands

The basic Git commands I use on a daily basis are listed below. If you read through the rest of this page in order, you can follow along by executing the same commands. By the end of this mini-tutorial, you'll have the latest version of the `Private-Code` repository on your local machine, and you'll even make your first contribution to our code base!

To proceed, you should be working in a Unix-based OS \(Mac OS or a [Linux](./) derivative\). Git comes pre-installed on most Debian-based Linux operating systems \(e.g. Ubuntu, elementary\). To my knowledge, if you are in a Mac OS you need to install Git from the [download page](https://git-scm.com/download/mac).

The first time you use Git, it will ask you to provide your name and email address. You can do this with the following commands. Instead of "Your Name" you would put your name \(e.g. Alex Reis\) and instead of "email@psu.edu" you would put your email \(e.g. alex.reis@psu.edu\).

```text
$ git config --global --user.name "Your Name"
$ git config --global --user.email "email@psu.edu"
```

If you forget to define your user.name and user.email, you won't get any further in this tutorial, because GitHub will demand that you run these two commands before you execute any others.

Note: For the purposes of this tutorial, were are working on the default branch only, `master`. Branches are were Git gets a bit more complicated. For our purposes, `master` is the branch of interest for us, although `Private-Code` has other branches \(e.g. `commercial`\). Branches are neat ways of working on different versions of the same repository from different `commit` points. Hang in there.

### clone

Clones a repository into a newly created directory, creates remote-tracking branches for each branch in the cloned repository \(visible using `git branch -r`\), and creates and checks out an initial branch that is forked from the cloned repository’s currently active branch.

Open `Terminal`. Use `git clone` to clone the `Private-Code` repository into your root directory.

```text
$ git clone https://github.com/hsalis/Private-Code.git
```

### pull

Incorporates changes from a remote repository into the current branch. In the case of using GitHub, you "pull" down any changes that other users have "pushed" to the GitHub hosted version of the repo.

First, step into the `Private-Code` directory, and then run a `git pull` now:

```text
cd Private-Code
/Private-Code$ git pull
```

Output:

```text
Already up-to-date.
```

This makes sense, because you just cloned the repository and downloaded all the files are are currently there. It is possible that within the few seconds between your `git clone` and your `git pull` commands, that someone in our lab pushed changes. In that case you would see a listing of the changed files that you just pulled down.

### status

Displays \(1\) paths \(files or directories\) that have differences between the index file and the current HEAD commit, \(2\) paths that have differences between the working tree and the index file, and paths in the working tree that are not tracked by Git.

A little confusing, I know. Just give it a try:

```text
/Private-Code$ git status
```

Output:

```text
On branch master
Your branch is up-to-date with 'origin/master'.
nothing to commit, working directory clean
```

Let's try two things:

\(STEP 1\) Open the file that renders this page \(Private-Code/protocol-book/01\_Linux/git.md\) in your favorite text editor. Make a change to this file by adding your name under [Git Masters](git.md#git-masters) exactly how I have my name formatted. Save the file. By the end of this tutorial, you're name will be here on this page! You will have become a Git master. Keep up the good work!

\(STEP 2\) Let's do one other thing. Make a dummy file in the root directory of `Private-Code` \(we'll delete it in a moment\):

```text
/Private-Code$ touch tutorial.txt
```

Now, run `git status` again:

```text
/Private-Code$ git status
```

You should see:

```text
On branch master
Your branch is up-to-date with 'origin/master'.
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

    modified:   protocol-book/01_Linux/git.md

Untracked files:
  (use "git add <file>..." to include in what will be committed)

    tutorial.txt

no changes added to commit (use "git add" and/or "git commit -a")
```

Because the first file \(`git.md`\) was an existing part of the repository and was being tracked, it is listed under "Changes not staged for commit". In other words, Git knows the file, and acknowledges that there are differences. Git also sees an unfamiliar file, `tutorial.txt`, and puts it under "Untracked files".

### diff

Show changes between the working tree and the index or a tree, changes between the index and a tree, changes between two trees, changes between two blob objects, or changes between two files on disk.

In other words, `git diff` shows you the changes between two files. If you simply specify `git diff <filename>` it will show you deletions and additions between your file and the file described by the local index on the same branch. Go ahead and run this command for the `git.md` file you added your name to.

```text
/Private-Code$ git diff protocol-book/01_Linux/git.md
```

Output should have something like this in it:

```diff
diff --git a/protocol-book/01_Linux/git.md b/protocol-book/01_Linux/git.md
index edb7b09..05591a1 100644
--- a/protocol-book/01_Linux/git.md
+++ b/protocol-book/01_Linux/git.md
@@ -1,3 +1,5 @@
 # Git
+* Your Name
\ No newline at end of file
```

You should see your name in green, which indicates that you added that line.

There is more complex usage to see the difference between your local repo and the GitHub hosted repository version, and so on. See [git diff](https://git-scm.com/docs/git-diff).

### add

This command updates the index using the current content found in the working tree, to prepare the content staged for the next commit.

You use `add` to tell `Git` which files you're ready to commit. When `add` is called with specific files or directories, only those specific files or folders get staged. This is handy because sometimes you don't want to commit all changes that you've made.

Add the `git.md` file to the index. You're ready to commit your change!

```text
/Private-Code$ git add protocol-book/01_Linux/git.md
```

There shouldn't be any output from `git add`, but run a subsequent `status`:

```text
/Private-Code$ git status
```

Output:

```text
On branch master
Your branch is up-to-date with 'origin/master'.
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

    modified:   protocol-book/01_Linux/git.md

Untracked files:
  (use "git add <file>..." to include in what will be committed)

    tutorial.txt
```

Here `Git` tells us that `git.md` is ready to be committed. Notice that `tutorial.txt` is still not staged, `Git` is still telling us if we want to add that file, we would need to run another `git add`.

Go ahead and delete `tutorial.txt` with `rm`. We don't need that file anymore.

```text
/Private-Code$ rm tutorial.txt
```

### commit

Stores the current contents of the index in a new commit along with a log message from the user describing the changes.

With `git commit` you are stepping forward in your local repository history to a new permenant change. If you add -m 'your text here' \(or --message='your text here'\) you can commit with a comment describing what you've done or changes that you've made. Let's try a git commit with a comment:

```text
/Private-Code$ git commit -m "Adding my name to the protocol-book git manpage."
```

Result:

```text
[master efa78ff] Adding my name to the protocol-book git manpage
 1 file changed, 3 insertions(+), 1 deletion(-)
```

Great! You've made your first `git commit`. If you try another `git status` command, `Git` should tell you the following:

```text
On branch master
Your branch is ahead of 'origin/master' by 1 commit.
  (use "git push" to publish your local commits)
nothing to commit, working directory clean
```

11/20/17 ACR I just discovered that you can use `-m` twice to get a title \(or summary\) and a description for your commit. This is more elegant than a single long message passed to git. This might be specific to Github. Not sure...

```text
/Private-Code$ git commit -m "Add Name: Alex" -m "Adding my name to the protocol-book git manpage. This is a part of the git tutorial!"
```

### push

Updates remote refs using local refs, while sending objects necessary to complete the given refs.

The command, `git push` allows you to "push" your local commits to the remote `GitHub` hosted version of the repository. You have to `push` to allow other users to acces your changes with a [`git pull`](git.md#pull). Notice the `git status` output following your `commit` above:

```text
Your branch is ahead of 'origin/master' by 1 commit.
```

Let's correct this with a push. `git push` can take arguments if you are pushing to a different branch, for example. For now, if you just put `git push`, your commits get pushed to origin/master, since you are also on branch master.

```text
/Private-Code$ git push
```

You should get some output that looks somewhat like this, confirming that the push was successful:

```text
Writing objects: 100% (6/6), 767 bytes | 0 bytes/s, done.
Total 6 (delta 5), reused 0 (delta 0)
remote: Resolving deltas: 100% (5/5), completed with 5 local objects.
To https://github.com/hsalis/Private-Code
   badda93..fd23da8  master -> master
```

### stash

Stash the changes in a dirty working directory away. Use git stash when you want to record the current state of the working directory and the index, but want to go back to a clean working directory. The command saves your local modifications away and reverts the working directory to match the HEAD commit.

Sometimes, you'll be working on some tracked files, but you need to `pull` a bunch of recent changes from the remote repository. If you try to pull immediately, `Git` will notice what is referred to as a `merge conflict` between the files you've changed and the corresponding files on the remote repo, without the changes. A good way of going about this, is to stash your current draft files, and then "unstash" with the following commands:

```text
/Private-Code$ git stash
/Private-Code$ git pull
```

Ok you've pulled the other changes. But we want your modified files back:

```text
/Private-Code$ git stash pop
```

If you do a `git status`, you should see your files listed under tracked files with changes.

### checkout

Updates files in the working tree to match the version in the index or the specified tree. If no paths are given, git checkout will also update HEAD to set the specified branch as the current branch.

I use this sometimes when I have a modified file that I don't want to keep, and instead I just want the latest version of this file on the remote repo. Easy enough:

```text
/Private-Code$ git checkout filename
```

## Git Masters

* Alex Reis

## Resources

* [Git documentation](https://git-scm.com/docs)
* [Getting Started - Git Basics](https://git-scm.com/book/en/v2/Getting-Started-Git-Basics)
* [What is Git](https://www.atlassian.com/git/tutorials/what-is-git)
* [git - the simple guide](http://rogerdudler.github.io/git-guide/)

There are many more commands and more complex usage of the commands that I've described above. I hope this basic guide helps get you started! -Alex

