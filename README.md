# orphanage

## setup
```
# Create orphan branch
git checkout --orphan main-project1
# Setup orphan branch to as you would a clean repo and remove all the main repo stuff
git add .
git commit -m "initial commit project1"
git push --set-upstream origin main-project1

# Setup orphan branch as a git submodule in main branch
git checkout main
git submodule add https://github.com/jlootensdataroots/orphanage ./projects/project1
git submodule set-branch --branch main-project1 projects/submodule1 

# Cloning the repo
git clone --recurse-submodules https://github.com/jlootensdataroots/orphanage.git
cd orphanage
git submodule update --remote # !!! set submodule branch to the one set previously (here main-project1) isntead of the default branch (main)
```