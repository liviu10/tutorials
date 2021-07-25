# Github for basic operations:

Access [official documentation](https://education.github.com/git-cheat-sheet-education.pdf "Github Cheat Sheet") to see all the available commands.

## A. <u>Branch List and Status Commands</u>:

1. Display a list of all local and remote branches:
   
    <span style="color:red; font-weight:bold;">
        <pre>
    <span style="color:white; font-weight:normal;"> (local branches):</span> git branch
    <span style="color:white; font-weight:normal;">(remote branches):</span> git remote</pre>
    </span>

2. Display which files were changed and not committed: 

    <span style="color:red; font-weight:bold;">
        <pre>
    <span style="color:white; font-weight:normal;"> (select branch):</span> git checkout branch_name
    <span style="color:white; font-weight:normal;"> (status branch):</span> git status</pre>
    </span>

## B. <u>Publish modifications on Github Repository Commands</u>:

1. Stage and Commit modified files:

    <span style="color:red; font-weight:bold;">
        <pre>
    <span style="color:white; font-weight:normal;"> (select branch):</span> git checkout branch_name
    <span style="color:white; font-weight:normal;"> (status branch):</span> git status
    <span style="color:white; font-weight:normal;">   (stage files):</span> git add ".\path\to\file(s)"
    <span style="color:white; font-weight:normal;">  (commit files):</span> git commit --message "..."</pre>
        <pre>
    <span style="color:white; font-weight:normal;">   (stage all):</span> git add --all
    <span style="color:white; font-weight:normal;">(stage folder):</span> git add ".\path\to\folder"</pre>
    </span>

2. Push modified files to your remote branch: 

    <span style="color:red; font-weight:bold;">
        <pre>
    <span style="color:white; font-weight:normal;"> (push branch):</span> git push origin branch_name</pre>
    </span>

3. Request a pull from local branch into master branch:

    <span style="color:red; font-weight:bold;">
        <pre>
    <span style="color:white; font-weight:normal;">      (pull request):</span> git request-pull branch_name url master
    <span style="color:white; font-weight:normal;">     (master branch):</span> git checkout master
    <span style="color:white; font-weight:normal;">(merge local branch):</span> git merge --no-ff branch_name
    <span style="color:white; font-weight:normal;">(push master branch):</span> git push origin master</pre>
    </span>

4. Pull modification into local branch:

    <span style="color:red; font-weight:bold;">
        <pre>
    <span style="color:white; font-weight:normal;">(pull request):</span> git pull origin master</pre>
    </span>
