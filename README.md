## To Run this Server (Tested on OSX 10.11 El Capitan)
 - Start by opening the terminal by pressing Command+Space and searching for the program terminal
 - Create SSH-RSA Keys
```
ssh-keygen -t rsa
```
 - Once you run this you will be asked some questions
```
Enter file in which to save the key (/home/demo/.ssh/id_rsa):
Enter passphrase (empty for no passphrase):
Enter same passphrase again:
```
 - Press Enter through the 3 prompts

## WARNING: Do not share your id_rsa (private key) file with anyone. It will allow others to impersonate you and log into your account
 - transfer your id_rsa.pub (public key) to the ecelinux server
```
scp ~/.ssh/id_rsa.pub <your-uw-id>@ecelinux.uwaterloo.ca:
```
 - Enter yes when prompted and Enter your quest password
 copy your public key into the appropriate folder
```
 ssh <your-uw-id>@ecelinux.uwaterloo.ca
 mkdir ~/.ssh
 mv ~/id_rsa.pub ~/.ssh/authorized_keys
 exit
```
 - You should now be able to log in without your password. You can test this by running
```
 ssh <your-uw-id>@ecelinux.uwaterloo.ca
 exit
```
 - Install MacFusion and its dependencies
