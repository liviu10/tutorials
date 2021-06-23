Github Terminal Commands

[Github Terminal Commands](https://education.github.com/git-cheat-sheet-education.pdf "Git Cheat Sheet") are a list of commands that are run in the terminal:

1. Display the status of all the branches and remotes:

   * display a list of all the branches on the local server:
    <span style="color:red; font-weight:bold;">
        <pre>git branch</pre>
    </span>

    * display the current active branch:
    <span style="color:red; font-weight:bold;">
        <pre>git status</pre>
    </span>

    * display a list of all the remotes:
    <span style="color:red; font-weight:bold;">
        <pre>git remote</pre>
    </span>

2. Create a new branch and move to that newly created branch:
   
    <span style="color:red; font-weight:bold;">
        <pre>git checkout -b new_branch_name</pre>
    </span>

3. Commit file(s) to the current active branch and merge branch with master:

   * select a specific branch:
    <span style="color:red; font-weight:bold;">
        <pre>git checkout branch_name</pre>
    </span>

   * stage file(s) for commit:
    <span style="color:red; font-weight:bold;">
        <pre>git add "path/to/file(s)"</pre>
    </span>

   * commit file(s) with a certain message:
    <span style="color:red; font-weight:bold;">
        <pre>git commit --message "..."</pre>
    </span>

   * push file(s) on the remote branch:
    <span style="color:red; font-weight:bold;">
        <pre>git push origin branch_name</pre>
    </span>

    * create the merge request directly on github account or:
    <span style="color:red; font-weight:bold;">
        <pre>(optional): git merge branch_name</pre>
    </span>

4. Pull modified file(s) to local branch_name:

   * select master branch:
    <span style="color:red; font-weight:bold;">
        <pre>git checkout master</pre>
    </span>

   * pull modified file(s) to local remote branch:
    <span style="color:red; font-weight:bold;">
        <pre>git pull origin master</pre>
    </span>

5. Create a new repository in terminal:

    <span style="color:red; font-weight:bold;">
        <pre>git init</pre>
    </span>
    <span style="color:red; font-weight:bold;">
        <pre>git add --all</pre>
    </span>
    <span style="color:red; font-weight:bold;">
        <pre>git commit --message "Message goes here"</pre>
    </span>
    <span style="color:red; font-weight:bold;">
        <pre>git remote add origin URL_TO_GITHUB_REPO</pre>
    </span>
    <span style="color:red; font-weight:bold;">
        <pre>git push -u origin master</pre>
    </span>

