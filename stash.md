# Git Stashing

## __Overview:__
Stashing allows you to save file changes for later without committing them. When you edit, add, or delete a file in your repository, typically you would stage and then commit. But what if you've accidentally been working on the wrong branch or just not ready to commit your changes? Then stashing is the option for you! 

Stashing saves uncommitted changes so you can work on other things inn your repository without losing your changes. It's also really useful for when you want to see how your code ran before you started making changes. If you had been using commits, you might have had had to use the ```python git reset --hard head^``` command but not with stashing. Unlike a commit, stashed code is also visible to all branches. 

## __How to Implement:__
You can use the following command to save your changes.  
```python
git stash save "stash message"
```

Your terminal should reply with the following message:

    Saved working directory and index state On BRANCH_NAME: "stash message"

    HEAD is now at HASH_OF_COMMIT_BEFORE_CHANGES initial again

Before stashing it can always be helpful to view the changes in your edited code and the last commit using the ```python git diff``` command.

If you want to see your previous stashes (similar to ```python git log``` for commits) you can use the list command
```python
git stash list
```
which will result in the following output (where i is the stash's index starting at 0)

    stash@{i}: On BRANCH_NAME: "stash message" 

When you're ready to reapply your saved changes, you can _apply_ or _pop_ your stash to your current branch. 
- apply takes the changes stored in a stash and apply them to your working directory while keeping your stash intact
  - ```python
    git stash apply stash{i}
    ```
- pop does the same thing as apply but deletes the stash after applying them to the working directory
  - ```python
    git stash pop stash{i}
    ```
If you do not specify an index for either commands, it will default to the first stash. 

You can also manually delete stashes using the drop command.
```python
git stash drop stash{i}
```
Remember that stashes are not commits and that even if you apply them, by dropping the stash it will disappear from your code as well. You must commit if you don't want the applied stash to be dropped. Stashing is useful for temporary storage but is not a replacement for committing changes.

There is also the clear command that deletes all stashes. 
```python
git stash clear 
```

## __Further Information:__
There are a lot more specified commands you can use with stashing. If that is something you are interested in I recommend checking one of the two following links:  
- [Git Tools Stashing and Cleaning](https://git-scm.com/book/fa/v2/Git-Tools-Stashing-and-Cleaning#:~:text=The%20answer%20to%20this%20issue,even%20on%20a%20different%20branch)
- [git-stash](https://git-scm.com/docs/git-stash)

## __Note:__
As of late 2017, 
```python
git stash save "stash message"
```
is being replaced with 
```python
git stash push "stash message"
```

## Sources:
- https://www.youtube.com/watch?v=KLEDKgMmbBI&ab_channel=CoreySchafer
- https://www.youtube.com/watch?v=Ie1EXmd9k0s&ab_channel=GitKraken
- https://git-scm.com/book/fa/v2/Git-Tools-Stashing-and-Cleaning#:~:text=The%20answer%20to%20this%20issue,even%20on%20a%20different%20branch
- https://git-scm.com/docs/git-stash

