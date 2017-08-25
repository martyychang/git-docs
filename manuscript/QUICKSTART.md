It's the first day where you're being asked to follow a Git workflow in a team environment,
but all you really want to do is build stuff.
You ask, "Why do things have to be so difficult?"

Avoiding the question trap, let's get down to business. All you gotta do is this.

1. Figure out your team's shared **integration branch**.
   For a brand new project, that shared integration branch may be `master`.
   For a major release in a live project, that shared integration branch may be
   something like `release-2.0`.
2. Check out (no, not ogle) the shared integration branch
   from your shared **remote repository**
3. Create a new feature branch _from_ the shared integration branch
4. Check out your new **feature branch**. Now you're ready to wreak... make changes!

Feel free to create and edit whatever you want, and even delete files!
Don't worry, as long as you're on your feature branch, you won't be hurting
anyone. And any unwanted changes you make _can_ be undone. Go ahead, blaze on!

5. Make some changes
6. Commit your changes to your feature branch
7. Repeat previous two steps until you're happy with your work
8. Push your feature branch to your remote repository
9. In your remote repository, create a pull request from your feature branch
   to your team's shared integration branch

Now, you can sit back, sip your coffee and wait for the peer review.
