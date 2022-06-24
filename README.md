# ado-commit-and-push

Even if it sounds simple, to push a commit inside an azure pipeline it's not so straight forward.

This is because azure checkouts the code in a detached head state by default, and there are some errors you find yourself into when trying to push to the branch you believe you're on but you aren't.

So, it's necessary to do the following
- fetch your branch
- create a new local branch to get out of the detached head state
- do a normal commit
- checkout your branch
- cherry-pick the commit to the feature branch the pipeline is running on
- push (finally)

There may be other ways, but this is the method I've found that works and I want to save this pipeline for future reference for myself, with a lot of debug messages that are usful when developing
