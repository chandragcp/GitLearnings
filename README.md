
Trying to put my important learnings or findings related to GIT and GIThub on Mac.

# Creating a new Repo

How to set up fresh git repo and create a git remote on local system with seamless pull and push.

It is always good to create new repo in Github and then synchronize it local machine.   While creating the repo, select the options to create both READMD.md and .gitignore files.

Once the repo is created in Github, you can create remote on local machine in multiple ways.

Please see the below article on managing the remore repositories:

    https://docs.github.com/en/get-started/getting-started-with-git/managing-remote-repositories

 To create the remote repo on local machine, I see the following options:

 01) By using the git remote

    git remote add origin <<REPO URL on GIThub>>

 02) By using the git clone

    git clone <<REPO URL on GIThub>>    

Though it appears git remote option is better choice here, but git clone seems working fine for me.     

# SSH setup for Git Repo

As most of you aware, GIT stopped supporting password authentication couple of years back.  Hence the only way to synchronize the repos between Github and local systems is SSH only.  

Below is the procedure to configure the SSH on both local systems and Github.

Please follow the steps mentioned in the following article to configure the SSH for GIT.

https://medium.com/codex/git-authentication-on-macos-setting-up-ssh-to-connect-to-your-github-account-d7f5df029320


After executing the steps mentioned in the above article, please test the SSH connection with the "_ssh -T git@github.com_" command .

    chandranakkalakunta@Chandras-MacBook-Air GitLearnings % _ssh -T git@github.com_
    Hi chandragcp! You've successfully authenticated, but GitHub does not provide shell access.

If the output is as shown above, which means SSH connection is successfully established between local mac system and Github.

However, when I tried to do "git push", it didn't work without configuring the set-url option for remote within the repo directory on local machine.   Many places this is not mentioned clearly, but this is critical for seamless push to gitbub.


    git remote set-url origin git@github.com:<GITID>/<REPOID>.git

Please see the below sample for my repo.

    git remote set-url origin git@github.com:chandragcp/TestRepo.git

 The above command need to set for every repo separately.

 



