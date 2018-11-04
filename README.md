# GitSSHTuttorial
Tutorial for adding SSH keys to github/bitbucket.

#Generate an SSH key

Using Git Bash Type the following commands

'''
$ ssh-keygen -t rsa -b 4096 -C "white@nwmissouri.edu"
Generating public/private rsa key pair.
Enter file in which to save the key (/c/Users/s123456/.ssh/id_rsa):
'''
Press enter to save the key to the defualt location.
You will then be prompted to enter a pass phrase for the private key you have just generated.

You will then need to add the SSH key to the ssh-agent. To do this type the following command in git bash:
'''
$ eval $(ssh-agent -s)
Agent pid 11111
$ ssh-add .ssh/id_rsa
'''

Before moving on to the Git Hub or Bitbucket page we need to copy the ssh key to the clip board, which can be be accomplished by opening the ssh key in a text editor or typing the following command:
'''
$ clip < .ssh/id_rsa.pub
'''

