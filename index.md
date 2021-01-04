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