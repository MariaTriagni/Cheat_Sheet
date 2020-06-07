
### steps to access repository using git
- make repository in github
- create readme
- go to c:\github

### clone repository from server to local
git clone https://github.com/MariaTriagni/TemplateProject_BackgroundProcess.git
cd TemplateProject_BackgroundProcess

### to see which file need to commit
git status
	
### to set user name in git config 
git config --global user.name "MariaTriagni"

### to set user email in git config 
git config --global user.email "agni199@gmail.com"

### to see all config in git
git config --list
	
### to add 1 file/folder for commit
git add pom.xml

### to add all file/folder for commit
git add -p

### commit the added file. you still not able to see the added file in repository
git commit -a -m "Initial commit"

### push to the repository. now you can see the added file in repository
git push origin master
	