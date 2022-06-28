# test_repository
This is a test repository. Only intended for practice and testing

The various codes are :

git commit -m "Adding file1, file2, file3"
#records changes to the repository. Creates a new commit containing the current contents of the index and the given log message describing the changes. The new commit is a direct child of HEAD, usually the tip of the current branch and the branch is updated to point to it ( unless no branch is associated with the working tree, in which case HEAD is detached as described in git-checkout(1)

git status

git add .
#Adds all file contents to the index. Updates the index using the current content found in the working tree, to prepare the  content staged for the next commit. The index holds a snapshot of the
#content of the working tree, and it is this snapshot that is taken as the  contents of the next commit

git add names.txt

git push -u origin main
#pushes the  committed filed in the local repository to the remote repository at the url specified by the origin (set using url data given on the github website) and on the branch specified as main

git remote add origin git@github.com:vishakhp/test_repository.git 
#For adding a new origin (i.e. a repository url/ssh)

git remote set-url origin git@github.com:vishakhp/test_repository.git
#For modifying the set (for modifying existing repository url)

git branch -M main

git branch # gives the current branch

git branch dev1
#creates a new branch called dev1

git checkout -b dev2
#creates a new branch called dev2 and switches to dev2 also.

git branch -d feature # removes the branch named feature

git pull origin main 
# Suppose you have merged a feature branch with the main branch and now you have merged it onto the main branch as
#well. But, in your local repository, the changes will not reflect by itself. you have to create a pull request now
#from the origin on the main branch onto your local repository

git checkout main
#swtiches the current branch to the branch - main

git branch
#Outputs the current branch

git branch dev1
#Creates a branch called dev1

git push origin feature
#pushes code on your local respository to the origin URL(which is available as SSH URL on the website) with the 
#branch specified as feature

git status
#returns the current  status of the files on your git repository

git remote -v
#gives the details of the origin
                      
git commit -am "message"
#Works only on modified files that have already been committed before. It adds the files to the staging area and commits at the same time.
#But the file must have been committed before

git stash
#stash your added files somewhere and thus no need to commit the  files

git reset file1.txt
#unstages the added file (which was added to stage via the command add file1.txt)

git reset HEAD~1
#HEAD is the pointer to the last commit. This command undoes the last done commit. HEAD will point to one commit further and hence ignores the latest commit

git log
#gives the log of all the recent changes including commits. Use the commit ids to reset to a particular change.
