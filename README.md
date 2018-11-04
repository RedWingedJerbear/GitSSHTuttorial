# GitSSHTuttorial
Tutorial for adding SSH keys to github/bitbucket.

## Generate an SSH key  

Using Git Bash Type the following command:

```
$ ssh-keygen -t rsa -b 4096 -C "white@nwmissouri.edu"
Generating public/private rsa key pair.
Enter file in which to save the key (/c/Users/s123456/.ssh/id_rsa):
```
Press enter to save the key to the defualt location.  
You will then be prompted to enter a pass phrase for the private key you have just generated.  

You will then need to add the SSH key to the ssh-agent. To do this type the following commands in git bash:  
```
$ eval $(ssh-agent -s)

$ ssh-add .ssh/id_rsa
```

Before moving on to the Git Hub or Bitbucket page we need to copy the ssh key to the clip board, which can be be accomplished by opening the ssh key in a text editor or typing the following command:
```
$ clip < .ssh/id_rsa.pub
```
## Add the SSH key to GitHub/Bitbucket 

### Go to your GitHub or Bitbucket page and click on your profile:     
![GitHub 01](img/github01.png) ![Bitbucket01](img/bitbucket01.png)

### Click on the settings option:  
![GitHub 02](img/github02.png) ![Bitbucket02](img/bitbucket02.png)

### Click the ssh key page:  
![GitHub 03](img/github03.png) ![Bitbucket03](img/bitbucket03.png)

### Click on the add ssh key option:  
![GitHub 04](img/github04.png) ![Bitbucket04](img/bitbucket04.png)

### Name your key and the paste the key which was copied to your clipboard earlier:  
![GitHub 05](img/github05.png) ![Bitbucket05](img/bitbucket05.png)

## Test your key

For GitHub type this command in git bash:  
```
$ ssh -T git@github.com
```

For Bitbucket type this command in git bash:  
```
$ ssh -T git@bitbucket.org
```

If you get an error you messed up somewhere. If you get no error message, **congratulations!**