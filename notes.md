## Initializing Git Repo
- Make a new folder where we want project to live make sure to cd into that folder. Once in correct folder run the following commands
    - git init (initializes the repo)
    - git add . 
    - git commit -m 'your message' 
    - git status (Should say 'nothing to commit working tree clean')

- Go to Github and create new repo
    - In setup on github use ...or push existing repo from command line. copy and paste code and run in terminal inside project folder.

-Add Collaborators
    - Navigate to 'settings' tab once there click on collaborators
    - Then click the green 'invite collaborator' button and add your collaborator.

# Branches

- When repo is created branch is named 'master' or 'main' by default. These branches refelct the production ready state (this is the code (mostly) that is being looked at when deploying an application)
    - Because our master/main branch is what is being looked at we don't want multiple members of a team all pushing their code to a singular master branch that contains deployed, working code. 
    - This is why we use branches

- To create a branch off of our master/main branch (which is provided by default from GitHub) 
    - Create develop branch first
        - Develop branch serves as an integration branch.
        - Each developers branch will first be merged with the develop branch
- To create the develop branch run these commands:
    - git branch (run first to check which branch you are currently in we should be on master/main)
    - git checkout -b develop (This will create the develop branch AND move us into that branch)
    - git branch (now we should see that we are in the develop branch)

- Switching branches 
    - git checkout <branch name> (This will switch between branches)
- Deleting a branch
    - git branch -d <branch name> (This will delete a branch)

- When we make a change to the development branch we run these commands:
    - git add .
    - git commit -m 'your message'
    - git push

- We don't want to push code that on our development branch to the master branch, so run this command
    - git push (we do this instead of git push origin master/main)

- Running git push will give up an error saying fatal: The current branch develop has no upstream branch. To push the current branch and set the remote as upstream, use git push --set-upstream origin develop
- Now we run the following command:
    - git push --set-upstream origin develop (This will set this will allow us to only push to the develop branch, so we can )
- Now if we make changes and run git push --set-upstream origin develop these changes will be pushed to the develop branch.
    -The process will be the same for branches that are off of the development branch

# Merging

- In browser navigate to the repo on github. There should be a branches button and tab where you can view all the branches.
- Click on the 'New pull request' button next to the branches button
- There will be two boxes:
    - Left box is the branch you are pushing to 
    - Right box is the branch you are pushing
- Once branches are selected press the 'Create pull request' button, You will then be redirected to a page where we can finialize the merge, and see if there are any conflicts.
- If there are no conflicts you are free to click the green 'Merge pull request' button.
- If successful you will see a box 'Pull request has been successfully merged and closed.'

# Merge Conflicts

- If you have merge conflicts github will give you an error message (this happens after selecting the branches to be merged)
- Now after clicking 'Create pull request' we are redirected to a new page with a prompt letting you know there are conflicts that must be resolved before merging.
- Click 'Resolve conflict' and you are redirected to a page that shows where the conflict is in your code and which branch each piece of conflicting code is coming from. 
- To fix the merge conflict remove the branch names preceding or succeeding the lines of code, and structure the code the way you want. 
- Once the conflicts are resolved click 'Mark as resolved' we should then be able to click a new green button to confirm the changes. 
- Finally we are redirected back to the previous screen and should now be able to click 'Merge pull request' followed by a 'Confirm merge' button. 

# Network insights

- On the github repo page we can click the 'insights' tab in the toolbar and select 'Network' This will show a timeling of each commit/merge.