# Local Repos
#delete #branch:
git branch -d branch_name

#revert #commit #back:
git reset --hard HEAD~1

#fatal #loose #object #corrupt:
rm -fr .git
git init
git remote add origin [your-git-remote-url]
git fetch
git reset --mixed origin/branch_name
git checkout -b branch_name
git branch --set-upstream-to=origin/branch_name branch_name
*NOTE, METHOD DOES NOT REQUIRE COPYING FILES*

#change #last #commit #rename:


# Remote repos

#store #credentials:

#pull #branch:
git fetch origin branch_name

#delete #remote #brahch: 
git push origin --delete branch_name

#remote #rename:
   git branch -m old-branch-name new-branch-name
   git push origin -f new-branch-name

#add #remote #url:

#revert #commit #back:
git reset --hard <commit_hash> # reset to some commit
git commit -am "reset"
git push --force

## #LFS (Large File Storage)

```
git lfs install
git lfs track "*.<your_file_extension>"
git config http.postBuffer 524288000
git commit -am "..."
git lfs migrate import --include="*.<your_file_extension>"
git push 
```