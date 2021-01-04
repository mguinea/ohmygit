Git is a great tool to maintain your project code but sometimes it turns into a mess if you make a mistake... and stress is guaranteed!

Here are some common situations I had to face when working with Git, and their solution approach.

# I have pushed a commit to the wrong branch

You can use this to change a correct commit pushed to the wrong expected branch. It is recommended if you are working
with multiple branches to run `git branch` becore each push to ensure you are in the correct one.

```bash
# You need to copy the commit hash. Check your git log to see the historic:
git log

# Here is an example:

# commit af63d8e7dfcfe2ac9796d4f7230f8459a6dc616e
# Author: Marc Guinea <develop.marcguinea@gmail.com>
# Date:   Wed Dec 30 22:37:54 2020 +0100
# 
#    Update _config.yml

# Go to the correct branch
git checkout branch-where-commit-should-be-pushed

# And run cherry pick
git cherry-pick your-copied-hash
```

# A bug has been introduced, but I don't know when

Using `bisect` you can find the commit where a bug was introduced. More info at [Git Documentation](https://git-scm.com/docs/git-bisect)

```bash
# Define range of commits to check
git bisect start bad_commit good_commit

# This will send you to a specific commit.
# If you find that the bug is not here, you must mark commit as good.
git bisect good

# Now, you are in another commit, if this is bad (for example), mark it as bad.
git bisect bad

# You will know that you are in the commit with the bug when 
# receiving following message:
# Bisecting: 0 revisions left to test after this

# Take note of the commit and exit bisect
git bisect reset
```