## Task 1:

Add a text file called version01.txt inside the Devops/Git/ with “This is first feature of our application” written inside.
This should be in a branch coming from `master`,
[hint try `git checkout -b dev`],
swithch to `dev` branch ( Make sure your commit message will reflect as "Added new feature").
[Hint use your knowledge of creating branches and Git commit command]

- version01.txt should reflect at local repo first followed by Remote repo for review.
  [Hint use your knowledge of Git push and git pull commands here]

Add new commit in `dev` branch after adding below mentioned content in Devops/Git/version01.txt:
While writing the file make sure you write these lines

- 1st line>> This is the bug fix in development branch
- Commit this with message “ Added feature2 in development branch”

- 2nd line>> This is gadbad code
- Commit this with message “ Added feature3 in development branch

- 3rd line>> This feature will gadbad everything from now.
- Commit with message “ Added feature4 in development branch

Restore the file to a previous version where the content should be “This is the bug fix in development branch”
[Hint use git revert or reset according to your knowledge]
A)done

## Task 2:

- Demonstrate the concept of branches with 2 or more branches with screenshot.
A) git branch
- add some changes to `dev` branch and merge that branch in `master`
A) vim >> verison01.txt >> all all >> git add commit >> git checkout main >> git merge dev

- as a practice try git rebase too, see what difference you get.
A)done
