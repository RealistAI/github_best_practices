# Common GitHub operations and their proper use

## git init
### What it does

Create an empty Git repository or reinitialize an existing one

### When to use it

When you want to make a preexisting project a GitHub repository.

### Why you use it

You would use it because it is the only way to create an empty repository or reinitialize one.<br>

## git clone <repo_name>
### What it does

Clones a git repository onto your Virtual Machine.

### When to use it

When starting the project for the very first time and you need the git repo.

### Why you use it

You would use git clone <repo_name> to get the repository you’re wanting to work with on your VM.<br>

## git pull
### What it does

Pulls the most recent changes from the GitHub master branch to your specific branch.

### When to use it

When you need to get the most recent changes made to the code and the changes were not made by you.

### Why you use it

You would use it because it’s the only way to get the most recent changes from GitHub.<br>

## git push
### What it does

It pushes your most recent changes to GitHub from the VM. 
It is best practice to push your changes to a branch that is not the master branch.

### When to use it

When you have finished your specific task and need to upload it to GitHub.

### Why you use it

You would use it because you want to push your most recent changes to GitHub.<br>

## git branch
### What it does 

Shows you which branch you are currently working in.

### When to use it

Use this when you are unsure of what branch you are in and need to know.

### Why you use it

You use it because you need to know the branch you’re working in, 
it would cause problems to share a branch with another developer.<br>

## git checkout <branch_name>
### What it does

Moves you to another branch, only works if the branch already exists. 
Otherwise, run the command git checkout -b <branch_name>, 
as it creates a new branch and moves you into that new branch.

### When to use it

Use this when you want to move into another branch and you know the branch exists already. 
or use git checkout -b <branch_name> when you are starting a new task 
and need a branch for that specific task.

### Why you use it

You would use it because it’s the only way to transfer to a pre-existing branch. 
Or use  git checkout -b <branch_name> 
because it is the only way of creating a branch and moving to it. <br>

## git branch -d <branch_name>
### What it does

Deletes the specified branch from your VM.

### When to use it

Use this when you have finished the task that the branch was created for. 
It will delete the branch which is best practice as it isn’t needed anymore.

### Why you use it

You would use it because it is in the GitHub best practices to 
delete a branch after the tasked being done on it is complete.<br>

## git add <file_to_add> 
### What it does 

Adds file to the stored index. You can add files by their specific name or 
by using a period “.”. a period adds all changes made within its tree.

### When to use it

you use it when you want to prepare a git push.

### Why you use it

you use it because this is the only way to push your changes to GitHub.<br>

## git commit -m <message_explaining_changes>
### What it does 

This records changes to the repository.

### When to use it

you use it when you have finished a specific task and 
you have added all the files need to the stored index. 

### Why you use it

You use it because if you don't record the changes to 
the repository it is impossible for a git push to be accomplished.<br>

## git status
### What it does

this shows the status of the working tree. 
so if you made changes you main.py it will reflect that in the git status command.

### When to use it

you use it when you want to know what files have you have changed so far.

### Why you use it

You use it if you have forgotten what files have been changed 
or if you want to confirm before doing a git commit.<br>

## git push --set-upstream <repo> <branch>
### What it does   

This sets the upstream for your current working branch. 
  That means it sets the destination for where it goes when you do a git push.

### When to use it

you use it when you first made a new branch and 
  GitHub needs to know where you want your content to go.

### Why you use it

GitHub will not allow you to push changes to a repository,
if it doesn't know what upstream you are using.
So you use it because it will not work otherwise.<br>

## git diff
### What it does

it shows the changes between commits, commit and working tree, etc.

### When to use it

you use it when you want to see the actual code changes 
between the working directory and the stored index

### Why you use it

You use it because it is a very helpful tool to see all the changes you made in the code 
on one screen and you can analyze the differences.<br>

## Scenarios for GitHub

### scenario 1:  

Miquel pene pequeno wants to clone his git repository, it is called pipeline_services. Miquel will run the command git clone https://github.com/GilbertTopia/pipeline_services.git, then it will clone the master branch of the repository to Miquels working vm. Miquel will then create a new working branch to work in. He will call the branch testing_pipeline. he will use the command git checkout -b testing_pipeline this will create the branch and move Miquel into it automatically. 

Now after making some tests for the pipeline Miquel wants to add all his changes to the repository. He will use the git add . command. This will add all the changes from every file in his current working directory, which is the files he changed so it does as he requires. Miquel runs a git status to confirm that everything looks as expected. Miquel now wants to commit his changes to the working repository, so he will use the git commit -m "Added pytesting for the pipeline service. I tested the functions and the service as a whole and it runs as expected" you will want to include as much detail as possible in your commit messages.

Next, Miquel needs to push the changes he has committed to the GitHub repository so he will run the command git push. This however will throw an error because Miquel has yet to tell GitHub where his branch is going to send its data. So Miquel will run the command 

git push --set-upstream https://github.com/GilbertTopia/pipeline_services.git testing_pipline

it will then ask him for his GitHub information, which he will enter and the data will successfully send to GitHub. 

Miquel then went to their GitHub repository and created a pull request, this is so his code can be reviewed by senior developer. shortly after, Miquel's code has been approved, so he had completed his task.

Miquel will then run the command git branch -d testing_pipeline to delete the branch he was working in, since his task as been completed there is no reason to use the branch.<br><br>

### scenario 2:  

Gregorius the Android created an application on his local VM and it worked fine for him this way for a long time. He eventually decided it would be best to make a git repository, so he ran the git init command on his take_over_the_world_by_frustrating_the_plans_of_merrik(what a mouthful) directory. This made his current directory a git repository. Then he ran the git add . to add all his changes to the staging area. He ran git status to confirm it was all there, and then ran the  git commit -m "the code to destroy all the plans of merrik mwahahahahaha" 

He then pushed all the changes to his new git repository by running the git push command. Gregorius knew he had to set the upstream if he wanted the push to work as expected.

git push --set-upstream https://github.com/GregoriusForPresident/take_over_the_world_by_frustrating_the_plans_of_merrik.git master  

Gregorius pushed all the code to the master branch because the repository didn't exist until he created it, thus it needed the master branch to create the foundation of the git repository.

Many months later, Gregorius' whole network had access to the code, His noble subordinate Phineas, ran a git pull command to get the most recent changes after being on vacation. This command easily gave him all the recent changes. Then Phineas ran the git branch destroy_merrik  to quickly swap into the proper branch to begin work.

After working on the code for a couple of hours, Phineas ran the git diff command to compare the changes he had made to what's in the working repository. He ran this command because it shows the actual code and what had changed and where status only shows the names of the files changed.

After comparing the changes and running the commands to add, commit and push his data. 

Phineas will then went to their GitHub repository and created a pull request, where Gregorius looked over his code. Gregorius approved the code so Phineas has completed his task.

Phineas deleted his branch as normal standard and then ran the git branch command to confirm he had deleted the branch and to show what branch he was in now. <br><br>

## Troubleshooting GitHub

## Trunk Based Deployment

## Feature Based Deployment
