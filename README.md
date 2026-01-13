# gh-actions-filter-bug
Reproducing a bug in Github Actions

If you look at the workflow file in this repo, you can see that there is a demo workflow that should only run when files matching `**/ios/**` change.

Looking at the commits, this workflow also runs when the file `src/portfolios/demo.txt` changes, which should not match the glob listed in the `paths` of the workflow file.

I posit that Github is treating `**/ios/**` as `*ios/**` instead and matching folders that end in "ios".

You should also see that the demo is not triggered when the change is made to this README.md file.
