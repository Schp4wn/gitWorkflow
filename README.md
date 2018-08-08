#GIT WORKFLOW

##01/ Initialization on Master
[GitHub: /]
Créer le repo "gitWorkflow"
[Console locale]
mkdir gitWorkflow
cd gitWorkflow
git init
git remote add origin https://github.com/Senvisage/gitWorkflow.git
echo "# gitWorkflow" >> README.md
git add README.md
git commit -m "First commit, initialization"
git push -u origin master

##02/ Creation of the Develop branch
[Console locale]
git checkout -b develop master
touch mockFile.txt
git add mockFile.txt
git commit -m "First commit for the develop branch"
git push -u origin develop

##03/ Creation of a Feature branch
[Console locale]
git checkout -b GW001 master
touch GW001.txt
git add GW001.txt
git commit -m "First commit for the feature branch"
git push -u origin GW001

##03/ Merge a Feature branch into Develop
[Console locale]
git checkout develop
git merge --no-ff GW001
git branch -d GW001
git push origin :GW001
git push

##05/ Merge Develop into Master (Pull request)
[GitHub: /branches]
Click "New Pull Request" on the feature branch
"Base: Develop" <- "Compare: GW001"
Click "Create Pull Request"
Click "Merge Pull Request"
Click "Confirm Merge"
Click "Delete Branch"
