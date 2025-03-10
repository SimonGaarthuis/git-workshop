## 0. install git

download: git-scm.com, or use your favourite package manager

## 1. initialize a repository

1. open a terminal, either cmd, bash, terminal, whatever
2. do some basic configuration:
    1. `git config --global user.name "Your Name"`
    2. `git config --global user.email your@email.com`
3. navigate to the folder you want your repositories to be
4. initialize an empty repository `git init demo`
5. download gitviz from https://github.com/riezebosch/gitviz/releases
6. open a second terminal and start gitviz providing the location of your repository:
    * e.g. `gitviz C:\some-path\git\demo`

## 2. basic snapshotting

1. add a file to the "working directory" of this new repository
2. start tracking the file using `git add <filename>`
3. see the blob appear in gitviz and/or the `.git/objects/` subfolder
4. check the status using `git status`
5. commit the staged files using `git commit -m 'your message'`
6. check the tree and commit appear
7. change the contents of the file
8. stage your changes using `git add`
9. commit the staged changes using `git commit`
10. check the updated graph in gitviz
11. rinse and repeat

## 3. branching and merging

1. create and checkout new branch
    1. either use `git branch feature/x` & `git checkout feature/x`
    2. or in one go using `git checkout -B feature/x`
    3. or use the new(ish) command `git switch -C feature/x`
2. do some modifications and commit the results
3. check the history (of current branch!) using `git log` or `git log --oneline`
4. switch back to your previous branch `git checkout -` or `git switch -`
5. create a new branch `feature/y`
6. do some other modifications and commit the results
7. switch back to your original branch
8. integrate both branches using `git merge feature/x feature/y`
9. watch the logs using `git log --decorate --graph --oneline`
10. delete both feature branches using `git branch -D feature/x feature/y`
11. watch the logs again using `git log --decorate --graph --oneline`

## 4. remotes

1. open a third terminal (or tab)
2. navigate to the directory where you want your repositories to reside
3. initialize a new repository and make it bare using `git init demo-bare.git --bare`
4. compare the directory structure with your original repository
5. switch to the terminal with your original repository
6. add the new bare repository as remote `git remote add origin ../demo-bare.git`
7. push your current branch into your remote named `origin` 
8. explore the contents of the bare repository
9. switch to the terminal where you have the bare repository open
10. check the git logs and branches