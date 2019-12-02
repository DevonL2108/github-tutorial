# GitHub Tutorial

_by Devon Lum_

---
## Git vs. GitHub
* Git
  * Manages code
  * Runs in the command line
  * Version control (Keeps _snapshots_ of code)
  * It is local unless you're using IDE
  * **Git does not require GitHub**  
  
* GitHub
  * Stores code to the cloud
  * Visually track changes 
  * Good for collaboration 
  * Runs in the command line 
  * **GitHub does require Git**


---
## Initial Setup
* Making a GitHub Account 
  1. Go to [github.com](https://github.com/)
  2. Enter a username (Something easy you can remember)
  3. Enter the email you normally use and a password
  4. Then click **Sign up for GitHub**
  
* Setting up your own IDE
  * You can simply [_click here_](https://github.com/hstatsep/ide50) to set up your own IDE  
  
> An **SSH** (Secure Shell) **key** is used to establish secure shell sessions between your computer and the insecure networks you access. It is highly needed because it is a key that only you can access and no one else can make changes to it. It is private and should not be shared. It is also used so you won't have to login to your GitHub account everytime you make a commit.


---
## Repository Setup
After you have setup your GitHub account and IDE you are ready to make your first repository.  
1. Go to your IDE and create a new directory `mkdir <file name>`
2. Cd into your new directory and type `git init`
   * `git init` changes your directory into a repository and creates a hidden _.git_ folder in the repository. It's like hiring a "photographer" but didn't add anything to the stage to take a photo of. To do `git init` you must create a new directory first and cd into it in order to do the command. **Don't do `git init` in the root directory.**
3. After you do `git init` add some files into the repository and modify them. Then, you would do `git add .` or `git add <file name>`
   * `git add` is getting files ready to be committed. It's like adding files to the stage, but didn't take a picture of it. You can only use this command if you created something new or modified anything in the repository.
4. After you did `git add` you would do `git commit -m "<commit message>"`
   * `git commit -m "<commit message>"` is committing everything you added on to the stage and creates a version history of your code. The concept is like after you added files onto the stage, you would then take a picture of the code and store it in your memory. The `m "<commit message>"` is an organized way to store your code. Your commit message shouldn't be too lengthy and tells exactly what you did or changed in that version of your code. It should also be in present tense. You're only able to use this command after you added files to the stage.
5. Now you would go to your GitHub account, click the **+** icon at the type right of your screen next to your profile picture and click **New repository**. Where you see **Repository name**, type in **exactly** what you named your directory in step 1. Then click **Create repository**. 
6. Under **Quick setup — if you’ve done this kind of thing before**, you should see a **HTTPS** and **SSH** button. Be sure to click the **SSH** button if it isn't selected already. Then, you would only want to focus on the **…or push an existing repository from the command line** section because you already created a repository. Under that section it should show:  
```
git remote add origin git@github.com:GitHubUsername/repository-name.git  
git push -u origin master
```
7. Copy and paste the first command into the command line of the repository that you cd into in step 2 and click enter. 
   * `git remote add origin <URL>` will create a remote/url for the repository to go to. In order to use this command, you must've already created a repository.
     * `remote` is like building a bridge to a destination, in which this case the destination is the URL or the name of your repository.
     * `origin` is the name of your repository. 
8. Copy and paste the second command into the command line of the repository that you cd into in step 2 and click enter.
   * `git push -u origin master` will push your commits to GitHub and will remember where you want to push to from now on. After you do this command, you can just do `git push` from now on. You can only do this command after you set up a remote.
     * `-u` mean upstream. It remembers where you want to push to.
9. Reload your GitHub page and you should see your first repo.

---
## Workflow & Commands
* While working on your Git project, it is important to do `git status` from time to time.
   * `git status` tells you the last changes you made. It tells you what is going on and what files are added to the stage and what aren't. It will also give you helpful commands like if you want to undo an edit or unadd something to the stage. Overall, this command is very useful throughout your workflow in Git. 

These are other common commands you would use throughout your workflow:
  
* If you are editing any files and want to add it to the stage to push it to GitHub, you'll use `git add`.  
  
* If you want to create a version of your code and go back to it from time to time you would use `git commit -m "<commit message>"`.
  
* If you want to push a version of your code to GitHub you would use `git push` (You may only use this command after you set up a remote in GitHub and made it your upstream).

---
## Rolling Back Changes
Throughout your workflow, sometimes you'll want to undo an edit, add, commit or push. Here's how you would do it:

* Lets say you edited a file and want to undo the edit you made in that file, you would do `git checkout -- <filename>`
  * 