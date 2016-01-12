## MacFusion Install Guide (Tested on OSX 10.11 El Capitan)
 - Start by opening the terminal by pressing Command+Space and searching for the program terminal
 - Create SSH-RSA Keys
```
ssh-keygen -t rsa
```
#### Once you run this you will be asked some questions
```
Enter file in which to save the key (/home/demo/.ssh/id_rsa):
Enter passphrase (empty for no passphrase):
Enter same passphrase again:
```
#### Press Enter through the 3 prompts

## WARNING: Do not share your id_rsa (private key) file with anyone. It will allow others to impersonate you and log into your account
 - transfer your id_rsa.pub (public key) to the ecelinux server
```
scp ~/.ssh/id_rsa.pub <your-uw-quest-id>@ecelinux.uwaterloo.ca:
```
 - Enter yes when prompted and Enter your quest password

#### copy your public key into the appropriate folder
```
 ssh <your-uw-quest-id>@ecelinux.uwaterloo.ca
 mkdir ~/.ssh
 mv ~/id_rsa.pub ~/.ssh/authorized_keys
 exit
```
#### You should now be able to log in without your password. You can test this by running
```
 ssh <your-uw-id>@ecelinux.uwaterloo.ca
 exit
```
#### Install MacFusion and its dependencies
 - Install MacFuse 2.8.2 http://sourceforge.net/projects/osxfuse/files/osxfuse-2.8.2/osxfuse-2.8.2.dmg/download (make sure you install the compatibility layer. It will be prompted during the install)
 - Install MacFusion https://github.com/ElDeveloper/macfusion2/releases/download/2.1-dev/Macfusion-2.1-dev.zip

#### Configuring MacFusion
 - Open MacFusion
 - Press the little (+) icon on the bottom left corner
 - select SSHFS
 - You can choose anything for the server name
 - enter ece.uwaterloo.ca for the "Host" field
 - enter your uw quest id for the "User Name" field
 - make sure you leave the password field blank and press ok
 - press the mount button on the main menu to mount the drive

#### Accessing the Mounted Drive
 - open finder
 - press command+shift+c to view all mounted drives
 - open the drive that is green
 - you can now use any text editor (e.g Sublime Text). When saving the file in the text editor, the file will automatically be updated on the server

#### Additional Info:
 - You can also use the terminal as a ssh client
 - to enter the server: run
```
ssh <your-uw-quest-id>@ecelinux.uwaterloo.ca
```
 - you can now run shell commands such as g++, vim, etc
