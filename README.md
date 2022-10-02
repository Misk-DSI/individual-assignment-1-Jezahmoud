# DSI 2022: Individual Assignment #1

This public repo was automatically generated by GitHub Classrooms and your instructors will use it to review your submission.

Please read the following instructions before beginning the assignment. **DO NOT** clone this repo at this this time.

## Learning Objectives

In class, we saw how to work with invited collaborators on the same repo in the same branch, `main`. Merge conflicts had to be dealt with manually, which is fine for small projects, but not for large ones. Here, you'll learn how to use **branches**, **forks** and **pull requests** to make collaborating less fraught with panic and easier to manage. These practical skills will be useful when working with your future colleagues as well as the up-coming group assignments.

Thus, although this is an individual assignment, you'll work in pairs with your _study buddy_. You can choose to work on the assignment side-by-side. If you don't have a study buddy or would like to change partners, please inform your TA promptly. Since your success depends on each other, don't leave it to the last minute.

The exercise is focused on understanding how to use tools on GitHub for working with a group of people (here, just two). In each pair, **both** students will complete **all** tasks. That is, you'll all be your own repo **owner** and, when needed, a contributor for your partner. Likewise, they'll do the same for you. 

## 1 - Repo Setup and Access (as an owner)

### 1.1 - Make a Local Repo

Although you already have this remote repo, your first task it access it by using the _Local First, Remote Second_ order. Open a terminal window and navigate to `Documents/misk_skills/`, your local folder containing the various course projects. Run the following commands: 

- Make a directory that has the same name as this repo, it should contain your GitHub user name.
- Initialize a git repo in the directory.

### 1.2 - Generate an SSH key for GitHub (if you have not done so already)

You don't need to create your own `README.md` file, since well take it from the remote repo. To connect your local repo and your remote repo, you'll need to access GitHub using SSH, Secure Shell Protocol. This is a widely used encryption protocol for networks and is generally accepted to be more secure than HTTPS, which you may have been using thus far to access your repos.

- Set your security pass by following the instructions [here](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent). 

### 1.3 - Authorize your SSH key for GitHub

- One you have completed all the steps to generate an SSH key, you'll be directed to authorize the [SSH key](https://docs.github.com/en/articles/authorizing-an-ssh-key-for-use-with-saml-single-sign-on)

### 1.4 - Access Remote Repo

- Link to this remote repo by replacing `<USERNAME>/<REPO>` with your details and run the following commands:

```
git remote add origin git@github.com:Misk-DSI/<REPO>.git
git pull git@github.com:Misk-DSI/<REPO> main
```

## 2 - Command Line Tools (as an owner)

Once you've pulled the remote repo, add some data. For this, we'll use data about the Covid-19 pandemic from the `WHO Coronavirus (COVID-19) Dashboard`. They are available as plain `csv` files. Complete the following:

- Create a directory called `data` and make it the working directory.
- Use `wget` to download the following files directly to the repository. **Do not** download the files manually from the website.

- Daily cases and deaths by date reported to WHO: `https://covid19.who.int/WHO-COVID-19-global-data.csv`
- Latest reported counts of cases and deaths: `https://covid19.who.int/WHO-COVID-19-global-table-data.csv`

After you've downloaded the data execute the following command, replacing `<USERNAME>` with your GitHub user name:

```
date "+%H:%M:%S %d/%m/%y <USERNAME>" > main_log.txt
```

- Add and commit your changes. To push, you'll need to first establish that the remote `main` branch is _upstream_ of the local `main` branch. Run the following command:

```
git push --set-upstream origin main
```

Your changes will appear in your remote repo.

## 3 - Making a Branch (as an owner)

Until now we've only worked on the `main` branch, which contains the _accepted_ work. A repo can have many branches, each designated for work on a part of the overall project. For example, there is a `feedback` branch in this repo which you're instructors will you to provide feedback on your assignment.  Since branch are separate and independent, changes on one branch won't interfere with any of the others.

In the console, make sure you're in your local repo and create a branch called `vaccine` for your partner by running the following command:

```
git branch vaccine
```

## 4 - Forking a repo (as a contributor)

Since you want people to work on your repo but you don't want to have to add them as a collaborator, which can be a dangrous thing, they can work on the new branch you've just created. By now your partner should have created a `vaccine` branche _for you to add to their project_ and shared their repo name with your.

- Go to your partner's repo and click the **fork** button. It's on the upper right, just below the page header.

Now that you have the `vaccine` fork of your partner's repo in your github account, you can do with it as you like.

- Clone your partner's repo and switch to the `vaccine` branch by running the following command:

```
git checkout vaccine
```

## 5 - Contribute Work (as a contributor)

- Make sure `data` is your working directory.
- Download the following two files using `wget`:

  - Vaccination data: https://covid19.who.int/who-data/vaccination-data.csv
  - Vaccination metadata: https://covid19.who.int/who-data/vaccination-metadata.csv

- After you've downloaded the data execute the following command, replacing `<USERNAME>` with your GitHub user name:

```
date "+%H:%M:%S %d/%m/%y <USERNAME>" > vaccine_log.txt
```

- Add, commit and push the changes.

Once you're done this, you'll have completed your contribution to your partner's project, but they still need to get your changes from your forked repo's `vaccine` branch. Let's get your work reviewed by the repo owner. 

## 6 - Pull Request (as a contributor)

When work on a branch is ready for review, a “Pull Request” (aka PR) is submitted on GitHub. This means exactly what it says. A person has forked your repo, made changes to their designated branch and now they've come to ask you to review their code.

- Go to your fork of your partner's repo on GitHub.
- Select the `vaccine` branch from the **Branch** pull-down menu.
- Click on the **Pull Request** button beside the **Branch** button.
- Enter a message to the repo owner, use `@` notation to address them directly, such as `@<USERNAME> I've made some updates, can you take a look?`
- Click **Submit Pull Request**.

## 7 - Reviewing and accepting a Pull Request (as an owner)

Once your partner has submitted a PR to _your_ repo (as you have done to theirs), you're ready to review it. 

- Go to your repo's GitHub page.
- You'll see an alert for your partner’s PR.
- Review your partner's work by clicking on the **Files Changed** tab.
- 
-This will show you, line-by-line, what code has been changed. You can even commment on the changes by hovering over a line number and clicking on the `+`. Alternatively, you can `git pull` the repo, `git checkout` to the forked branch and check it out on your local computer. For our purposes, the web interface will suffice.

- To accept the changes, click on **Merge this PR**. The forked repo will be included in the `main` branch.
