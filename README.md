# A quick crash course in branching

Branches confuse the heck out of me, mostly because I haven't had a *real* reason to use them. B helped walk me through a practice session to start familiarizing myself with the general workflow. I'm documenting my notes here for future reference.

### Steps (at least the steps we took in this practice example):

1. Sam created a GitHub Repository called [git-branch-practice](https://github.com/samanthacsik/git-branch-practice) and invited Brendan as a collaborator. There are no files yet in this respository. Brendan cloned the repo to his computer.
2. Sam & Brendan each create their own branches on their computers (**NOTE:** Brendan recommends naming branches using the following convention: `githubUserName/featureName`)

`$ git checkout -b samanthacsik/feature1` (**NOTE:** `git checkout` is used to change branches; the `-b` flag is used to create a new branch; when combined, it creates a new branch and moves to that new branch)

3. Sam and Brendan each create a file(s) on their local machines on their respective branches. Then stage, commit, push files *and* branches to the GitHub repo:

* `git add file_name`  
* `git commit -m "commit message"`
* `git push -u origin samanthacsik/feature1` (**NOTE:** `-u` stands for *upstream*; git will prompt you to use these commands (rather than `git push`) because the branch you just created is not yet on the remote)

4. Navigate back to the GitHub repo and click on "Pull requests." We chose to first address my (Sam's) PR first. Click on "Compare & pull request" for Sam's PR. This will open up an editor to add a description of your PR. Then click "Create pull request."

* Navigate to "Insights" -> "Network" to explore a visualization of your branches/merges
* Navigate to "Pull requests" -> "Files changed" to check out what changes have been done on this particular PR

<img width="1136" alt="Screen Shot 2021-10-25 at 8 44 01 AM" src="https://user-images.githubusercontent.com/43836046/138729376-5689283c-a42f-4c29-8b11-7f20c1561b1f.png">
5. Click "Merge pull request". 

6. At this point, Sam's changes on her `samanthacsik/feature1` branch have been merged back into `main`. Brendan **does not** yet have these new changes to `main` on his branch, `brendanshanny/brendans-branch`. Brendan must take the following steps to get those changes onto his branch before merging into `main`.

* `git checkotu main` (switches Brendan to his `main` branch)
* `git pull` (pulls changes from the remote `main` to his local `main`)
* `git checkout brendanshanny/brendans-feature` (switch back to his branch)
* `git merge main` (merge changes on `main` into his branch; **NOTE:** `rebase` is a better alterntive to `merge`, however we didn't cover this because I was getting confused (lol))
* **NOTE:** This process will open up Vim, a text editor. Vim is weird as hell (to a non-Vim user). Your PR title will automatically be added as a commit message in this case, so all you need to do is "write and quit" using the command `:wq`
* `git push`

Take a look at "Insights" -> "Network" again to see branches, commits, merges:

<img width="791" alt="Screen Shot 2021-10-25 at 9 21 59 AM" src="https://user-images.githubusercontent.com/43836046/138733383-c082c91a-dd4f-40bc-b7b0-69af6869482a.png">

**Some notes on Vim:**
* `esc`: quit Vim
* `:` enter command window
* `i`: insert
* `w` write
* `q`: quit



