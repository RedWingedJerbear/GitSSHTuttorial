# GitSSHTuttorial
Tutorial for adding SSH keys to github/bitbucket.

## Prerequisites
[Git for Windows](https://git-scm.com/downloads)  
[PuTTY](https://www.putty.org/)  
[PuTTYgen](http://www.puttygen.com/)  
GitHub Account  
Bitbucket Account  

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
```
```
$ ssh-add .ssh/id_rsa
```
To be able to use this key with TortoiseGit you will need to add it to Putty.  
You will need to create a Putty version of the private key. First open PuttyGen and click **conversions** and **import key** from the drop down menu. Browse to the _id_rsa_ key and click open. After this you will click **Save private key**, give a name and the file extension **`.ppk`**:  
![puttygen](img/puttygen.PNG)  
Next add the converted key to putty under Connections > SSH > Auth:  
![Putty 01](img/putty01.PNG)  

Then save the key under Session and default settings:  
![Putty 02](img/putty02.PNG)  

Before moving on to the Git Hub or Bitbucket page we need to copy the ssh key to the clip board, which can be be accomplished by opening the ssh key in a text editor or typing the following command:
```
$ clip < .ssh/id_rsa.pub
```
## Add the SSH key to GitHub/Bitbucket 

### Go to your GitHub or Bitbucket page and click on your profile:     
GitHub            :  
![GitHub 01](img/github01.png)  
Bitbucket:  
![Bitbucket01](img/bitbucket01.png)

### Click on the settings option:  
GitHub:  
![GitHub 02](img/github02.png)  
Bitbucket:  
![Bitbucket02](img/bitbucket02.png)

### Click the ssh key page:  
GitHub :  
![GitHub 03](img/github03.png)  
Bitbucket :  
![Bitbucket03](img/bitbucket03.png)

### Click on the add ssh key option:  
GitHub:  
![GitHub 04](img/github04.png)  
Bitbucket:  
![Bitbucket04](img/bitbucket04.png)

### Name your key and the paste the key which was copied to your clipboard earlier:  
GitHub:  
![GitHub 05](img/github05.png)  
Bitbucket:  
![Bitbucket05](img/bitbucket05.png)

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
 