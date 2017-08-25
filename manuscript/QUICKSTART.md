It's the first day where you're being asked to follow a Git workflow
in a team environment, but all you really want to do is build stuff.
You ask, "Why do things have to be so difficult?"

Avoiding the question trap, let's get down to business. All you gotta do is this.

1. Clone your team's shared **remote repository**
2. Figure out your team's shared **integration branch**.
   For a brand new project, that shared integration branch may be `master`.
   For a major release in a live project, that shared integration branch may be
   something like `release-2.0`.
3. **Check out** (no, not ogle) the shared integration branch
   from your shared remote repository
4. Create a new **feature branch** _from_ the shared integration branch
5. Check out your new feature branch. Now you're ready to wreak... make changes!

Feel free to create and edit whatever you want, and even delete files!
Don't worry, as long as you're on your feature branch, you won't be hurting
anyone. And any unwanted changes you make _can_ be undone. Go ahead, blaze on!

6.  Make some changes
7.  **Commit** your changes to your feature branch
8.  Repeat previous two steps until you're happy with your work
9.  **Push** your feature branch to your remote repository
10. In your remote repository, create a **pull request** from your feature branch
    to your team's shared integration branch

Now, you can sit back, sip your coffee and wait for the peer review.

## Try it out

Don't just sit there. Try it out, using this repository right here!
Imagine that you are part of the team who maintains this book,
and start by taking the first step.

### Clone the remote repository

Open your **command line interface** ("CLI") that has Git installed,
and let's clone the repository into your workspace directory.
Need a quick CLI primer? Flip to the CLI chapter of this book.

```sh
git clone https://github.com/martyychang/git-docs.git
```

This will create a directory named "git-docs" in your current directory.

### Figure out your integration branch

We keep things simple here, so our shared integration branch
is simply `master`.

### Check out the integration branch

Type the following command.

```sh
git checkout master
```

The first time you do this will be rather moot, since you should
already be on the `master` branch by default. Just to make sure
you _are_ on the `master` branch as expected...

```sh
git status
```

You should see output like the following.

```
On branch master
Your branch is up-to-date with 'origin/master'.
nothing to commit, working tree clean
```

### Create a new feature branch

Let's say you want to create a feature branch to sign the guest list
in this book. For simplicity, let's name the branch after your initials.
For example, if your name is Adam Benjamin Coddington, you'd name your
branch simply as `abc`.

Type the command below to create your branch.

```sh
git branch abc
```

If you get no errors, you're probably in the clear. You can prove
to yourself that you did indeed creat a new branch.

```sh
git branch
```

You'll see something like the following, with the asterisk indicating
the branch you're currently standing on.

```
  abc
* master
```

### Check out your feature branch

How do you move over to your new feature branch? Simple.

```
git checkout abc
```

To **check out** a branch means to switch over to that branch.
When you make changes to a file, you're only making changes to
that file _on your current branch_. You can verify this later
after you've made some edits.

For now, just be sure you did indeed check out the right branch.

```
git status
```

Git should tell you that you're standing on the `abc` branch.

```
On branch abc
nothing to commit, working tree clean
```

### Make some changes!

All right! Time to tear up the guest list chapter!
Open the **manuscript/GUESTS.md** file in your favorite text editor
and add your name somewhere inside the file. Once you're done
save your changes in the text editor, and go back to the CLI.

```
git status
```

Git will now tell you there are uncommitted changes.

```
On branch abc
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

        modified:   manuscript/GUESTS.md

no changes added to commit (use "git add" and/or "git commit -a")
```

Well, if the changes are uncommitted, the next logical step would be
to commit the changes, right?

### Commit your changes

Generally speaking, committing changes is a two-step process.
First, **add** the changed files you want to commit. Then, actually
**commit** the changes with a message.

```
git add manuscript/GUESTS.md
```

This explicitly adds the file you just modified to Git's short-term
memory, which now remembers exactly what you want to commit.

```
git commit -m "I added my name"
```

The plain English you see in quotes there is called the **commit message**,
which is an explanation of the incremental change you made. And
the commit itself is basically a logical set of instructions for
repeating the changes you made.

Confused? Don't overthink it right now, and let's move on.

### Make more changes

I forgot to tell you to also include your favorite quote when
adding your name to the guest list. Open the **manuscripts/GUESTS.md**
file again in your favorite text editor, and write a fun quote or
"lorem ipsum" next to your name. Once you're done
save your changes in the text editor, and go back to the CLI.

```
git status
```

Git will tell you once again there are uncommitted changes.

```
On branch abc
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

        modified:   manuscript/GUESTS.md

no changes added to commit (use "git add" and/or "git commit -a")
```

You know how to handle this, right?

### Commit the new changes

```
git add .
```

The `.` is a shorthand way of telling Git to add all of the changes
to all files that were made, so they can _all_ be committed.

```
git commit -m "my favorite quote"
```

Now you've made your second commit. Good job!

### Push your feature branch

All of the things you've been doing has been happening on your
machine and your machine alone. Obviously neither I nor the rest
of our team have access to your machine, so once you're ready
to share your changes with the rest of the team, you should
**push** your feature branch to our shared **remote repository**.

```
git push origin abc -u
```

Why `origin`? When you clone a repository, by default Git
will remember this remote repository as `origin`. When you talk
to people familiar with Git, everyone will know when you say
`origin` that you mean the remote repository from which your
local repository was _cloned_.

Don't worry about the `-u` for now. Just get in the habit of
adding this to the end of your `git push` commands.

Anyway, now your branch should be visible in the remote repository
on GitHub, where you can go to create the pull request!

### Create the pull request

Open the remote repository on GitHub by opening the repository's URL.

https://github.com/martyychang/git-docs

Once there, click the **Pull requests** tab, and then click the
**New pull request** button. A pull request is basically your request
for the hard work you've done to be included or **merged** into your
team's shared integration branch. Once merged, your work will have
been accepted by your teammates, and your contribution will be consecrated,
visible and celebrated for all time.

But where were we... Oh, yeah, the pull request.

On GitHub, the **base** branch is the branch into which you want your
work to be merged. The **compare** branch should be the feature branch
containing _your_ work. Make the appropriate branch selections, then
click **Create pull request**. Fill in the fields with some useful fluff,
then click **Create pull request** again like you mean it.

All right! Now the ball's in your peer reviewer's court. Bravo!
