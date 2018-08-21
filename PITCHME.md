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
