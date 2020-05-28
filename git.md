# git
## SSH Windows 10
1. Generate SSH keys using `ssh-keygen -t rsa -b 4096 -C "<address>@users.noreply.github.com"`
    - Create public and private key with password ie `~/<user>/.ssh/id_rsa` and `~/<user>/.ssh/id_rsa.pub`
2. Add the public ssh to the remote ie [github](https://github.com/settings/keys)
3. Change existing repos from https to ssh,
    - Check remote `git remote -v`
    - Change remote to ssh `git remote set-url origin git@hostname:username/repo.git` ie `git remote set-url origin git@github:LochMess/notes.git`
4. Add your ssh key to the windows ssh client so you don't have to use your ssh password for every commit. `ssh-add C:\Users\<username>\.ssh\id_rsa`
5. Set windows 10 OpenSSH client to start on start up, Start > Services > OpenSSH Authentication Agent > Properties > Startup type: Automatic (Delayed Start)
Use windows 10 openssh client, add to start up lazy start
6. Configure git to use windows 10 openssh client, `git config --global core.sshCommand C:/Windows/System32/OpenSSH/ssh.exe`
