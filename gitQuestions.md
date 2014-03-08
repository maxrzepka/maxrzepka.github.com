Q How to correct last commit log message ?
A  git commit --amend -m "Corrected Message"

Q How to run multiple apps on heroku from the same git repository ?
A http://tanyanam.com/technology/multiple-apps-on-heroku-from-the-same-git-repository

Q How to diff 2 branches ? (stat view)
A git diff --stat --color branch1..branch2

max@x300:~/Arbeit/clojure/cube$ git push
conq: repository does not exist.
fatal: The remote end hung up unexpectedly
max@x300:~/Arbeit/clojure/cube$ git remote -v
origin                          git@bitbucket.org:mrzepka/cube.git (fetch)
origin                          git@bitbucket.org:mrzepka/cube.git (push)
max@x300:~/Arbeit/clojure/cube$ git remote rm origin
max@x300:~/Arbeit/clojure/cube$ git remote add origin git@bitbucket.org:maxrzepka/cube.git
max@x300:~/Arbeit/clojure/cube$ git push origin console


Q How to work on other remote branches ?
A list all remotes branches : git branch -a
A check it out : git checkout origin/experimental
A checkout and work on it : git checkout -b experimental origin/experimental
A to track more than one remote repository : git remote add win32 git://example.com/users/joe/myproject-win32-port
A to see what's going : gitk --all &
A http://stackoverflow.com/questions/67699/how-do-i-clone-all-remote-branches-with-git

Q How to merge ?
A git checkout <main branch>
A git merge <new branch>
A git branch -d hotfix remove new branch (optionally)

Q stashing in short
A git stash : create a stash if local changes
A git stash list
A git stash show stash@{0}
A git stash apply
A git stash drop
A git stash pop : apply + drop
A git stash branch my_branch_name <stash> : apply and create a branch on success

Q How to list commited files only ?
A git ls-files <dir>

Q How to publish pages on github ?
A git checkout --orphan gh-pages
A git rm -rf .
A first 2 commands only the beginning then to push your changes
A git commit -m "sth " -a
A git push origin gh-pages

Q How to push your project to heroku ?
A heroku create --stack cedar
A git push heroku master

Q How extend password timeout when pushing to github ?
A  git config --global credential.helper 'cache --timeout=3600'

Q Branching commands ?
A git branch : list available branch
A git checkout <branch name> : change branch
A git checkout -b <branch name> : create branch and check it out


Q Does git follows logs when moving and renaming files ?
A yes  shorcut git mv

Q How to split a repository ?
A git clone <your project>
A cd <your project>
A git filter-branch --prune-empty --subdirectory-filter <directory you want to extract> master

Q Define Git remote host in github and push change to it ?
A git remote add origin git@github.com:username/Hello-World.git
A git push origin master

Q List remote
A git remote -v
