# GIT AND GITHUB
## GITHUB

Github is designed for project management. It's a place on the internet for us to host our own projects for collaboration with other developers and managing our projects. This is also known as our remote repository.

#### Branches
In a way Github also tells the story of how your project was created and how the developers added to it.

Branches allow us to safely added features to our project. We can switch to a branch in github add a change. If we don't like that change, we can move out of that branch and delete it to start over without harming our project.

Github is also like a tree where you can see kind of a timeline of what was added and what branches added what features.
```
        links-> added navigation bar-> 
master->                             merged with master
```

Here this tells the story of how in the project, you switched to the branch called links, added a navigation bar, it was successful so it was merged with master branch.

#### Commits

Commiting to your repo is another way of creating a timeline within a branch. Whenever you commit all of your work is basically saved to what we call an SHA key.

You add the files you want to save to your commit and give your commit a message describing a summerized detail on what you added.

You can modify your github directly on github by clicking the edit button while viewing a file in your github file tree. Once edited you can give it a commit message and save it which will automatically, however the best practice is using `git commands` in your terminal. If you have a local setup you can use your computers terminal. If you are using the `learn ide`. You will need the downloaded version and will be using the `temperary` directory as the root for creating your project.

You can view all of your commits by clicking on the commits link above the branch dropdown (which is above the file tree) in github to view all of your commits done in that branch.

Commit often!

#### Git Commands

The way we talk to our remote (github) repository is through git commands.

We can easily connect a local repo to our github repo from our command line.

The easiest way I've found to do it is to first initialize our local repository (local meaning the repo on our computer (not github))

```
mkdir new-project
cd new-project
git init
```

This will create a `.git` folder in our repository that will hold all of our repository data.

Next we'll create a `README.md` that is used by github to describe our project.

```
touch README.md
add some details to the README.md and save
```

Then you would want to add the files and create a commit message

```
git add .
git commit -m 'initial commit'
```

Next you would want to create a github repository. If you navigate to your github, on the first page on the bottom right, you'll see a blue button `new repository`. When you click that, you would give it a name, a description (optional), and then click on create.

Once the github repository has been created, search for the line in the first snippet that has `git remote add origin <your remote repo>`. Copy that line and paste it into your terminal. What this line does is connects your local repository to github.

Lastely you would push your local copy to github.

```
git push -u origin master
```

This sets the upstream meaning that it's pushing your local files that have been commited to github. You can refresh your github repository and you'll see it's been updated! Setting the upstream during this push connects your master branch (local) to the master branch on github and will only need to be connected once. 

After it's been connected you can simply `git push` which will automatically push to that branch.

If you are on another branch and want to add that branch to github, when you go to push in that branch you'll want to `git push -u origin master` for the first push to set it's upstream to that branch. It's a way of connecting branches.

#### GIT Cheatsheet

`git init` - creates .git in your local project
`git add .` - adds all files
`git add <filename>` - adds a particular file
`git commit -m 'message'` - adds a commit, (can only be done after adding files)
`git remote add <destination> <github url>` - will add the the push / pull destination to your project
`git remote set-url <destination> <github url>` - will override the original destination to your project
`git push -u origin <branch>` - will push and connect/create to a branch on github
`git push` - adds the commits and updates your remote github repository
`git push -f` - will push to github, -f means it will force the push. So if you get any issues where it wants you to pull from your repo and you know that your repo is current and working, you can override this step by adding `-f` to your push. (use with caution)
`git merge <branch>` - will merge the `current branch` and the specified `<branch>`. Usually we merge to master as master is what keeps all of our updates. So if we just updated our `nav` branch. We could `git co master` and then `git merge nav` to merge those changes.

#### terminal commands
`cd <folder name>` - will place you inside of a folder in your project
`cd ..` - will go out of the folder in your project into the parent folder
`touch <filename>` - will create a file in your project
`mkdir <foldername>` - will create a folder in your project