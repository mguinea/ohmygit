Git is a great tool to maintain your project code but sometimes it turns into a mess if you make a mistake... and stress is guaranteed!

Here are some common situations I had to face when working with Git, and their solution approach.

# I have pushed a commit to the wrong branch

```bash
git log
# You will see your history. Then, copy the commit hash. Here is an example:
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