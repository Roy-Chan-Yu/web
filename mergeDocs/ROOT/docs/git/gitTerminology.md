## Git Terminology 術語

`Some Commonly used terms`

### Branch
- A branch is a version of the repository that diverges from the main working project.
- an `essential feature available in most modern version control systems`.
- have more than one branch.
- perform many operations on Git branch-like `rename, list, delete`, etc.

### Checkout
- used for `the act of switching` between different version of a target entity.
- used to `switch between branches in a repository`.

### Cherry-Picking(重要) 
- In case you made a mistake and `committed a change into the wrong branch`, <font color="red">but do not want to merge the whole branch</font>. You can `revert the commit and cherry-pick it on another branch`.

### Clone
- used to make a copy of the target repository or clone it.
- want to copy of my repository from GitHub,the tool `allows creating a local copy of repository on your local directory from` <font color="red">the repository URL</font>.

### Fetch 
- `fetch branches and tags from one or more other repositories`, along with the objects `necessary to complete their histories`. It updates <font color="red">the remote-tracking branches.</font>

### HEAD
- the representation of the last commit in the current checkout branch.(the head like a current branch)
- When you switch branches with git checkout, the HEAD revision refer to the new branch.

### Index
- is a <font color="red">staging area</font> `between the working directory and repository`.
- used as the `index to build up a set of changes` that you want to commit together.


### Master
- `Naming convention` for Git `branch`.
- The resulting local repository contains `only a single local branch called a "Master" branch`.

### Merge
- take the data created by git branch and `integrate them into a single branch`.

### Origin
- a reference to the remote repository from a project was initially cloned.

### Pull/Pull Request
- `fetches and merges changes on the remote server to your working directory`.
- <font color="red">Pull request</font> announces all the team members that they `need to review the code and merge it into the master branch `.

### Push
- refers to `upload local repository` content to a remote repository.
- an act of transer commits from local to remote repository.
- Pushing is <font color="red">capable of overwriting changes.</font>

### Rebase
- referred to as the process of `moving or combining a sequence of commits` to `a new base` commit.
- is beneficial and visialized the process in the environment of `a feature branching workflow`.

