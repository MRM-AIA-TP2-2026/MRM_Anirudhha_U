# Task 1

## Installation
I first installed Ubuntu 22.04 on my system<br>
Then i installed Git using `sudo apt install git `<br>

## Configure Git
To set Name and Email id i used <br>
`git config --global user.name "Your Name"`
`git config --global user.email "your-email@example.com"`

## Connecting GitHub with my local system 
Then i created a repository in GitHub website. Then generated a public token which i used as a password to link git hub with my local computer.<br>
Then i used <br>`git init` in the terminal to Initialize a Git Repository then used <br>`git remote -v` to check the remote linkage.<br>
I used <br>`git remote add origin https://github.com/YOUR_USERNAME/YOUR_REPOSITORY.git` to make a new repo linkage.

## Procedure
Then i created a folder called GitHub_task using 
`mkdir GitHub_task`<br>
Then i wrote a script inside it and made it into a python file using the command<br>
`echo "print('Hello World')" > hello.py`
then to add the changes, i used <br>`git add .`
used <br>`git status` to check status of the files/folders. Then used <br>`git commit -m "hello.py is successfully committed"` to commit the changes.<br>
at the end i pushed `git push origin master`<br>
then i checked the github website and the folder wit the file was updated

## Reference
ChatGPT, Mentors
