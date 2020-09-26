create branch from old commit  
`git branch <name> a9c146a09505837ec03b`

add new branch to remote  
`git push -u origin feature_branch_name`

copy a file from another branch  
`git checkout otherbranch myfile.txt`

if behind a firewall use:  
`git config --global url."https://".insteadOf git://`

to make github work with git on windows 7 you need to generate a key with git for windows and set a username and password  
`git config --global user.name "username"`  
`git config --global user.email "myemail"`  
and then you need to paste the key in github website. then you can clone  

keep the credentials  
`git config --global credential.helper cache`

change a remote  
`git remote set-url origin somegiturl`

discard all changes you made since last commit  
`git reset --hard`

revert to specific commit  
`git revert 073791e7dd71b90daa853b2c5acc2c925f02dbc6`

tag a specific point in time  
`git tag -a v1 -m "first edition"; git push origin v1`

delete a remote branch  
`git push origin --delete branch`  

remove tracked file  
`git rm --cached filename`  

keep tracked file without commiting changes  
`git update-index --assume-unchanged file`  

checkout remote branch
`git fetch origin name && git checkout name `

pull unrelated histories for first commits
`git pull origin master --allow-unrelated-histories`

add remote origin
`git remote add origin https://bitbucket/xxx`

git clone speficic branch
`git clone --branch <branchname> <remote-repo-url>`

