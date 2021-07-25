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
    <span style="color:white; font-weight:normal;">   (stage files):</span> git add ".\path\to\file(s)_or_folder(s)"
    <span style="color:white; font-weight:normal;">  (commit files):</span> git commit --message "..."</pre>
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
    <span style="color:white; font-weight:normal;">      (pull request):</span> git pull origin master
    <span style="color:white; font-weight:normal;">(merge local branch):</span> git merge --no-ff branch_name
    <span style="color:white; font-weight:normal;">(push master branch):</span> git push origin master</pre>
    </span>

## C. <u>Other Commands</u>:

<span style="color:red; font-weight:bold;">
    <pre>
<span style="color:white; font-weight:normal;">       (stage all):</span> git add -a
<span style="color:white; font-weight:normal;">    (commit files):</span> git commit -m "..."
<span style="color:white; font-weight:normal;">     (stash files):</span> git stash
<span style="color:white; font-weight:normal;">(drop stash files):</span> git stash drop
<span style="color:white; font-weight:normal;">   (unstage files):</span> git reset ".\path\to\file(s)"
<span style="color:white; font-weight:normal;">    (show history):</span> git log</pre>
</span>