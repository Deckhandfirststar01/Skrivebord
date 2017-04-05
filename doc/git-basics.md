Editing the spec using git
==========================

Overview
--------

1. [Introduction](#introduction)
1. [Update repository](#update-repository)
1. [Create feature branch](#create-feature-branch)
1. [Make changes](#make-changes)
1. [Commit changes](#commit-changes)
1. [Comparing branches](#comparing-branches)
1. [Push branch](#push-branch)
1. [Pull request](#pull-request)
1. [How to link to a specific version](#how-to-link-to-a-specific-version)
1. [Working with WIP commits](#working-with-wip-commits)

### Introduction

For the purpose of this demonstration we'll suppose we want to specify the *firstRun* page of the desktop extensions.

For more information on git see <https://git-scm.com/book/en/v2/>.

### Update repository

Open terminal and go to the repository. If you don't have a repository read [How to setup grip and github on osx](/doc/grip-github-osx.md) first.

```
cd ~/Desktop/spec
```

![git_1.png](/res/doc/git-basics/git_1.png)

Fetch latest changes using.

```
git fetch
```
![git_2.png](/res/doc/git-basics/git_2.png)

Update master branch

```
git checkout master # Not necessary if already in master branch
git rebase origin/master
```
![git_3.png](/res/doc/git-basics/git_3.png)

<https://git-scm.com/book/en/v2/Git-Basics-Working-with-Remotes>

### Create feature branch

A branch is an alternate timeline used to develop changes without affecting the master timeline until the changes are ready. If the changes are ready (finished, reviewed and approved by all parties) the get merged back into the master branch.

You can think of a branch as a stack of post-its, each post-it representing a single change to the repository and each stack of post-its representing a different branch. The post-its are always in the order you stacked them on top of each other, the one you put on last will always be the top post-it, older ones are at the bottom.

For more infos on branches see <https://git-scm.com/book/en/v2/Git-Branching-Branches-in-a-Nutshell#_git_branching>

```
git checkout -b 1337_first_run master
```
![git_4.png](/res/doc/git-basics/git_4.png)

Make sure your local master branch is up to date (see [Update repository](#update-repository)) or use the following shortcut to create a the feature branch regardless of where you are currently at.

```
git fetch origin
git checkout -b 1337_first_run origin/master
```

![git_4_1.png](/res/doc/git-basics/git_4_1.png)

This creates a new branch named *1337_first_run* from the *master* branch

The new branch *1337_first_run* is a descendent of *master* and as such is on the same state as the *master* branch until you commit a change.

In post-its, the master branch is a stack of yellow post-its, the feature branch *1337_first_run* is a stack of pink post-its on top of the yellow stack, but until you stacked a new pink post-it on top they are virtually identical.

It's generally a god idea to create a branch for each change you are working on. The name of the branch should reflect the change and help you to quickly recall which branch is for which purpose. In development (and perhaps soon for all work on eyeo) a change originates in a ticket, so it makes sense to prepent the ticket id in the branch name. In this case imagine there would be a hub ticket with the id 1337.

<https://git-scm.com/book/en/v2/Git-Branching-Branches-in-a-Nutshell>

### Make changes


Now create the file *~/Desktop/spec/spec/abp/first-run.md* with the following content.


```
First run page
==============

The first run page will be shorn after the extension has been installed.

It should look like this:

![firstRun.html](/res/abp/first-run/first-run.png)

Show the text `Adblock Plus has been installed`.

...

Then show a button labeled `Get Adblock Brwoser here`. The button should be linked to <https://adblockbrowser.org/?ref=frp>.
```


Then open a terminal to run grip to preview your changes

```
$ cd ~/Desktop/spec
$ grip
 * Running on http://localhost:6419/ (Press CTRL+C to quit)
```

![grip_1.png](/res/doc/git-basics/grip_1.png)


Open a browser and visit <http://localhost:6419/spec/abp/first-run.md>

![grip_2.png](/res/doc/git-basics/grip_2.png)

The terminal should output:

![grip_3.png](/res/doc/git-basics/grip_3.png)

We have added the layout to *first run* specification but it doesn't show because
we haven't created it yet. So open the *first run* page in you browser, make a screen shot and save it under *~/Desktop/spec/res/abp/first-run/first-run.png*

(In chrome go to the options page and in the url change options.html to firstRun.html)

The result should look something like that.

![grip_4.png](/res/doc/git-basics/grip_4.png)

<https://git-scm.com/book/en/v2/Git-Basics-Recording-Changes-to-the-Repository>

### Commit changes

Now that we have made the changes we have to commit them.

To commit the changes we have to add them using `git add` and then commit them using `git commit`.

The command `git status` shows us where we're currently at. It shows the branch `1337_first_run` and changes we have made. We have created two files first-run.md and first-run.png but because git doesn't now these files yet it only shows the folders which contain new files (git calles them untrackked files because they are not under version control).

NOTE: To make sure we are on the right track it's generally a good idea to issue a `git status` after every command. This will visualize what git is doing and help us understand everything.

![git_5.png](/res/doc/git-basics/git_5.png)

Now add the the two new files.

`git add res/abp/first-run/first-run.png`

![git_6.png](/res/doc/git-basics/git_6.png)

`git status`

![git_7.png](/res/doc/git-basics/git_7.png)

`git add spec/abp/first-run.md`

![git_8.png](/res/doc/git-basics/git_8.png)

`git status`

![git_9.png](/res/doc/git-basics/git_9.png)

Now we have added the changes and will commit them.

`git commit`

This will open the text editor nano (might differ depending on your confifuration).

![git_10.png](/res/doc/git-basics/git_10.png)

Now type in a commit message reflecting the changes you have made. In this case we have added an initial draft of the first run page and as we have a ticket id it makes sense we include them in the commit message.

*Issue 1337 - Added initial draft of the first run page*

![git_11.png](/res/doc/git-basics/git_11.png)

Now we save the file and exit the editor using *Ctrl+X*.

![git_12.png](/res/doc/git-basics/git_12.png)

Then *Y*.

![git_13.png](/res/doc/git-basics/git_13.png)

Then *ENTER*.

![git_14.png](/res/doc/git-basics/git_14.png)

Verify using *git status*

`git status`

![git_15.png](/res/doc/git-basics/git_15.png)

Now we have put our first pink post-it on top of the yellow post-it stack and *1337_first_run* and *master* are no longer identical.

<https://git-scm.com/book/en/v2/Git-Basics-Recording-Changes-to-the-Repository>

### Comparing branches

To compare different stacks of post-its we can use *git log BRANCHNAME*

The *master* branch contains two commits (post-its), each post-it has a unique identify called the commit hash, an author, a date and the commit message describing the change.

```bash
$ git log master 
commit d587b9223fe8511dab95cbfe10e808a5fff964ed
Author: Winsley von Spee <winsley@adblockplus.org>
Date:   Tue Feb 14 11:40:59 2017 +0100

    Added initial draft of the "How to spec" guide

commit 7822c8016ca85991bf04e001b30a6e09f1e58de0
Author: Winsley von Spee <winsley@adblockplus.org>
Date:   Tue Feb 14 11:34:28 2017 +0100

    Added README.md
```

![git_21.png](/res/doc/git-basics/git_21.png)

Out feature branch *1337_first_run* contains one additional commit.

```bash
commit 8d1e8d785deb132e540ad4123893ddaff87b533a
Author: Winsley von Spee <winsley@adblockplus.org>
Date:   Sat Mar 4 13:19:10 2017 +0100

    Issue 1337 - Added initial draft of the first run page

commit d587b9223fe8511dab95cbfe10e808a5fff964ed
Author: Winsley von Spee <winsley@adblockplus.org>
Date:   Tue Feb 14 11:40:59 2017 +0100

    Added initial draft of the "How to spec" guide

commit 7822c8016ca85991bf04e001b30a6e09f1e58de0
Author: Winsley von Spee <winsley@adblockplus.org>
Date:   Tue Feb 14 11:34:28 2017 +0100

    Added README.md
```

![git_22.png](/res/doc/git-basics/git_22.png)

We can also show only the commits that we added to the feature branch (only the pink ones) by telling git we want all commits between *master* and *1337_first_run*.

```bash
$ git log master..1337_first_run 
commit 8d1e8d785deb132e540ad4123893ddaff87b533a
Author: Winsley von Spee <winsley@adblockplus.org>
Date:   Sat Mar 4 13:19:10 2017 +0100

    Issue 1337 - Added initial draft of the first run page
```

![git_24.png](/res/doc/git-basics/git_24.png)

We can also see what whe changed using *git diff*.

The command *git diff BRANCHNAME* shows the difference between *BRANCHNAME* and the currently checkedout branch, in this case *1337_first_run*.

```bash
$ git diff master 
diff --git a/res/abp/first-run/first-run.png b/res/abp/first-run/first-run.png
new file mode 100644
index 0000000..578bc30
Binary files /dev/null and b/res/abp/first-run/first-run.png differ
diff --git a/spec/abp/first-run.md b/spec/abp/first-run.md
new file mode 100644
index 0000000..d114900
--- /dev/null
+++ b/spec/abp/first-run.md
@@ -0,0 +1,14 @@
+First run page
+==============
+
+The first run page will be shorn after the extension has been installed.
+
+It should look like this:
+
+![firstRun.html](/res/abp/first-run/first-run.png)
+
+Show the text `Adblock Plus has been installed`.
+
+...
+
+Then show a button labeled `Get Adblock Brwoser here`. The button should be linked to <https://adblockbrowser.org/?ref=frp>.

```

![git_25.png](/res/doc/git-basics/git_25.png)

This command also demonstrates two important aspects about git.

Unless otherwhise specified everything is relative to the current branch.

The two commands

`git diff master`

and

`git diff master..1337_first_run`

are the same as long as *1337_first_run* is the current branch.

And second, whenever the output doesn't fit into the terminal *git* uses *less* to show the output (as indicated by the colon followed by the cursor at the bottom of the terminal).

And second, whenever the output wouldn't fit into the terminal window *git* starts to use scrolling. This indicated by the colon followed by the cursor at the bottom of the terminal. You can scroll using *Page Up/Down* or the *Arrow keys* and you have to type *q* to exit.

Note how the prompt is only displayed after pressing *q*.

![git_26.png](/res/doc/git-basics/git_26.png)

### Push branch

Now we publish our changes by pushing them onto the repository on <https://github.com>.

When we cloned the repository git has automatically created a reference to the original reposity called *origin*. So whenever we want to talk to the repository on <https://github.com> we use the remote name *origin*.

And we have to tell git what we want to push so we also supply our feature branch name `1337_first_run`.

`git push origin 1337_first_run`

![git_16.png](/res/doc/git-basics/git_16.png)

Now our changes have been pushed to <https://github.com>.

<https://git-scm.com/book/en/v2/Git-Basics-Working-with-Remotes#_pushing_remotes>

### Further changes

The *first run* specification is not yet finished. To continue working on it we first have to make sure everything is up to date (Suppose a few days have passed since the last step).

So got to [Update repository](#update-repository) and repeat the steps to update the *master* branch.

If our master branch is up to date, we have to update our feature branch *1337_first_run*.

First we switch to *1337_first_run*.

```bash
$ git checkout 1337_first_run
Switched to branch '1337_first_run'
```

![git_17.png](/res/doc/git-basics/git_17.png)

Then we rebase our feature branch *1337_first_run* on top of the *master* branch.

In post-its this means we have to put every new post-it that was added on top of the original yellow post-its stack (*master*) between the yellow and pink post-its in the feature branch *1337_first_run*.

To to that we call *git rebase*. It rebases the current checkout branch (*1337_first_run*) on top of the branch we specify, in this case *master*.

```bash
$ git rebase master
Current branch 1337_first_run is up to date.
```

![git_18.png](/res/doc/git-basics/git_18.png)

(In this case nothing has changed)


Now that everything is up to date we go ahead and make our changes.


Open the file *~/Desktop/spec/spec/abp/first-run.md* and specify the *Contributor Credits* link at the bottom of the page.

```markdown

Add the bottom of the page show the link [Contributor Credits](https://adblockplus.org/redirect?link=contributors&lang=en-US)
```

![grip_5.png](/res/doc/git-basics/grip_5.png)

Verify with *git status*

```bash
$ git status
On branch 1337_first_run
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

        modified:   spec/abp/first-run.md

no changes added to commit (use "git add" and/or "git commit -a")
```

![git_19.png](/res/doc/git-basics/git_19.png)

Now that git knows the file it shows that changes where made to a specific file. To know what exactly changed we call *git diff*.

```bash
$ git diff
diff --git a/spec/abp/first-run.md b/spec/abp/first-run.md
index d114900..b78cbdc 100644
--- a/spec/abp/first-run.md
+++ b/spec/abp/first-run.md
@@ -12,3 +12,5 @@ Show the text `Adblock Plus has been installed`.
 ...
 
 Then show a button labeled `Get Adblock Brwoser here`. The button should be linked to <https://adblockbrowser.org/?ref=frp>.
+
+Add the bottom of the page show the link [Contributor Credits](https://adblockplus.org/redirect?link=contributors&lang=en-US)
```

![git_20.png](/res/doc/git-basics/git_20.png)

If we're happy we add and commit the changes as described in [Commit changes](#commit-changes) and push the changes as described in [Push branch](#push-branch).

<https://git-scm.com/book/en/v2/Git-Basics-Recording-Changes-to-the-Repository>

### Pull request

Now that we have pushed our changes we will create a pull request for our changes.

A pull request is a way for the contributor (in this case you) to indicate that he has made some changes he wants to add.

It provides a plattform to review and discuss the changes he proposes.

In this step we'll make sure that the new changes adhere to the documents styleguide. Are links marked as such? Are texts marked as texts. Headings? Etc.? Basically all formal requirements get checked in this step.

(Currently we have no styleguide, but we'll develop one while we start to add more and more to the specification).

And also to make sure the the change makes sense and doesn't introduce and conceptual problems.

Because of the complexity of the document (the specification will necessarily be at least as complex as the program it specifies) it's important to have this step to flesh out as many errors as possible and ensure that the specification will not become a mess over time.

(This guide is probably a good example as it's probably riddled with errors and unnecessarily hard to understand in places ;))

This is the responsibility of the maintainer of the repository, for code repositories at eyeo this would be the module owner, for specifications the author of the spec (see *How to spec One author*).

The author of the spec should be the product manager (you) but it probably makes sense for me to handle it at the start and hand it over as you become more comfortable with *git* and *md*.


Goto <https://github.com/wspee/spec> to request our changes.

Then click on *New pull request* (the *compare & pull request* button can be used as a shortcut but will not always be there).

![github_1.png](/res/doc/git-basics/github_1.png)

Then you have to choose which stack you want to put on which stack. In this case we want to put the pink stack *1337_first_run* ontop of the yellow stack *master*. So we choose *master* as the base and compare it to *1337_first_run*.

![github_2.png](/res/doc/git-basics/github_2.png)

Github then allows as to describe the changes, so we put in a meaningfull text describing the change and referencing a ticket if any.

Below github shows the commits that have been added to the pink stack *1337_first_run* (*git log master..1337_first_run*) and also the changes that where made (*git diff master*)

Then we click *Create pull request*.

![github_3.png](/res/doc/git-basics/github_3.png)

Then the pull request has been succfully created. And it's time to open a beer :).

(Github will notify the maintainer of the repo about the new pull request).

![github_4.png](/res/doc/git-basics/github_4.png)

<https://git-scm.com/book/en/v2/GitHub-Account-Setup-and-Configuration>

## How to link to a specific version

If you share a link to the specification it makes sence to link to current (or a specific version) instead of the most recent version. This way the link will always show the version you were talking about at the time and not change randomly. For example imagine a ticket that tracks the implementation of a certain spec document. If you look at the ticket after a year the spec document will probably have changed and the ticket will no longer make sense.

Most recent version of this document:

<https://github.com/wvspee/spec/blob/master/doc/how-to-spec.md>

Current version of this document:

<https://github.com/wvspee/spec/blob/d587b9223fe8511dab95cbfe10e808a5fff964ed/doc/how-to-spec.md>

Note how the url has changed, instead of *master* it now contains long alphanumeric number (the commit hash). This number is like a version number of the repository and allows you to refer to a specific version of the repository (the whole repository not only a single file).

You can abbreviate the commit hash by trimming it down to 6 characters:

<https://github.com/wvspee/spec/blob/d587b9/doc/how-to-spec.md>

![How to link to a specific version](/res/doc/git-basics/link-to-a-specific-version.gif)

1. Find specific version in history
1. Click link on the right to view repository at the specific version
1. Open document
1. Copy link from address bar
1. Paste link where ever you need it

### Working with WIP commits

Sometime while you're working on a bigger feature branch you want to make changes to other parts of the specification without loosing you work in progress but also without committing and pushing you work in progress.

To do that you can create a temporary *WIP commit* you'll later undo so you can continue where you left of.

![Working with WIP commits](/res/doc/git-basics/working-with-wip-commits.gif)

1. Add all changes using `git add -A`
1. Commit changes to *WIP commit* `git commit -m WIP`
1. Create and swicth to other branch `git checkout -b 1338_other_thing origin/master`
1. Do the temporary thing
1. Switch back to original branch `git checkout 1337_first_run`
1. Undo *WIP commit* git reset HEAD^
