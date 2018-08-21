# Git Flow
## Intro and Demo

---

# What?
Branching strategy 

First described in 2010 by Vincent Dreissen

[Blog post](https://nvie.com/posts/a-successful-git-branching-model/)

---

# Why?

1. Separates the ongoing development from finished work. 
2. Makes it easier to collaborate on features. 
3. Has a release staging area
4. Emergency fixes are more manageable

---

# How?

--- 

### The main branches

<div class="mainbranches left">
![main branches](img/mainbranches.png)
</div>

<div class="right">
    <ul>
        <li>2 Branches. Master and develop</li>
        <li>Master always reflects the production ready state</li>
        <li>Develop reflects the current work towards the next release</li>
        <li>When develop reaches a stable state <b>all</b> changes are merged into master</li>
    </ul>
</div>

---

### The supporting branches 

<div>
    <ul>
        <li>Feature branches</li>
        <li>Release branches</li>
        <li>Hot-fix branches</li>
        <li>(Support) branches</li>
    </ul>
</div>

---

### Feature branches

<div class="left featurebranch">
![feature branch](img/featurebranch.png)
</div>

<div class="right">
    <ul>
        <li>Used to develop new features for the next or a future release</li>
        <li>Can branch off develop or other feature branches</li>
        <li>Always merge into develop</li>
        <li>Exists for as long as the feature is in development</li>
    </ul>
</div>

---

### Creating and using a feature branch

```
# Create a new feature branch
$ git checkout -b feature/my-new-feature develop
#Develop your feature when ready merge your changes

$ git checkout develop
Switched to branch 'develop'

# Merge your changes into develop
$ git merge --no-ff feature/my-new-feature
Updating ...
(summary of changes)

# Delete feature branch
$ git branch -d feature/my-new-feature
Deleted branch feature/my-new-feature ...

# Push your changes to origin
$ git push origin develop

```

--- 

### Release branches

<div class="left releasebranch">
![Release branch](img/releasebranch.png)
</div>
<div class="right">
    <ul>
        <li>Used to prepare a new release. Last minute bug fixes can be done on the release branch</li>
        <li>All features that are supposed to be in the release must be in develop when the branch is created</li>
        <li>Branches off develop</li>     
        <li>Must merge back into develop and master</li>
    </ul>
</div>

--- 

### Creating and using release branches

```
# Create the new release branch
$ git checkout -b release/1.1 develop

# Bump any version number (if needed in your workflow)

$ ./bump-version 1.1
Version bumped to 1.1

$ git commit -a -m 'Bumped version to 1.1'

# Do any testing in the UAT environment. Any bugs discovered should be fixed directly on the release branch, not develop.

```

---

### Finishing a release

```

# Merge to master

$ git checkout master
Switched to branch 'master'
$ git merge --no-ff release/1.1
...
(summary of changes)
# Tag release commit with version number for future reference
$ git tag -a 1.1

# Merge changes to develop

$ git checkout develop
$ git merge --no-ff release/1.1

# Delete release
$ git branch -d release/1.1

```

--- 

### Hotfix branches

