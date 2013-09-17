<img src="../images/IXM-Transparent-Vertical.jpg" style="float:right; margin:-10px 15px 0 0;" height="90" />
![Indiana State University logo](../images/isu_logo.png)

# Keeping your repo up-to-date

## Forked, now what?

You've forked the isu_primary repository from the base ImageX source GitHub account. You've cloned the repository to your local machine from your GitHub account. Now what?

## The problem

Whether or not you're doing active development on the actual codebase, you would like to keep your code up-to-date with the main 'dev' branch of the ImageX source repo. You're not quite sure what the best way is of doing this, and you may have even tried re-forking the repo just to get the latest changes.

## You're in luck

Git is a distributed source control tool, which helps to make it perfectly suited to solve your problem. There is a relatively simple way for you to keep your local machine's repository up-to-date with the latest development improvements ImageX is making day-after-day.

## Git remotes

Git uses something called 'remotes' to manage connections between your copy of a repository and other copies located in other locations. When you cloned the repository from your GitHub account's fork of the main isu_primary repo, the clone auto-generated a single remote linking it back to your GitHub account's copy of the repository. What this means is that you can use the 'git pull' and 'git push' commands to pull and push changes between your local copy and your GitHub copy.

(In the same vein, when you originally forked the repo to your GitHub account, a 'remote' was created linking your fork back to the source isu_primary repository.)

The good news is that you're not limited to this one 'remote'. In fact, a git repository can have unlimited remotes. To create a new 'remote', you simply run the following command:

```git remote add [name you'd like to call your remote] [remote address]```

Here's an example for adding a remote connecting your repository back to the main isu_primary repo:

```git remote add upstream git@github.com:imagex/isu_primary.git```

After adding a remote, you can see your new remote by running:

```git remote```

And see the remote address details by running

```git remote -v```

## Git remote workflow

Adding the remote is the simple part. What we really need is a workflow to follow to incorporate the changes from this new remote into our local repository. As a result, what we need to do is periodically pull down the changes from this new remote so that they keep the local version up-to-date with the latest changes.

To do so, you simply pull changes like you would from your own GitHub fork, but this time you specify the remote to pull from:

```git pull [remote name] [branch name]```

An example of pulling the latest dev changes from the isu_primary main repo using the 'upstream' remote you just created:

```git pull upstream dev```

What this command does is pull from the upstream remote's repository, specifying to pull from the 'dev' branch of that repository, and merges what it pulls down into the current branch you're on of your local repository. Provided you haven't made any local changes that conflict, this is all there is to it and you'll have the latest greatest from the codebase.

## Drupal requires a bit more

*** This section covers more advanced topics, and doesn't try very hard to simplify them because they are legitimately quite complex. As a result, don't worry if it doesn't make sense right now or you don't know what to do with the information. At a later point you may find it useful to refer back to. ***

Drupal is a complex piece of software with many moving parts. This complicates things because it's not as simple as just changing the code and having those changes reflected immediately in all cases. For instance, Drupal uses multiple different layers and types of caching to optimize performance. As a result, changes you make to code do not always become implemented in the site immediately because they have been cached. Therefore, at a minimum, after pulling the latest changes you should clear all of the site's caches.

In addition to caching issues, the workflow ImageX uses (along with most serious Drupal development) heavily employs Drupal's 'features' module to store site configuration in code (rather than in the database). By default, Drupal would store these configurations in the database. When features are being used and changes are made to the configuration, those changes are stored in the database unless they're explicitly exported back to code. What this means for pulling down the latest code is that it usually results in features being overridden by the database because Drupal sees two conflicting configurations but always preferences the database state. To resolve this, you may also need to revert all features when you pull down the latest changes (it's best practice to get in the habit of doing this whenever you merge new code).











