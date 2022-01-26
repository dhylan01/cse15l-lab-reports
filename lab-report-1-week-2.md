# Week 1 & 2 lab reports

### Installing VScode

   -[Download VS Code](https://code.visualstudio.com/download)
   ![Image](vsCodeDownload.png)

   - Once downloaded, open the package and follow prompts on the screen. Click next past for all of the prompts given without making any changes unless they present immediate problems. The screen should then look like this when you open it:
     ![Image](sc1.png)

## Remotely Connecting
   - When remotely connecting, first start by finding your emote account email. This can be done through the link: https://sdacs.ucsd.edu/~icc/index.php . Next type in your username (the text before the @ sign of your ucsd email adress) and Student ID (with the A or U) and click the submit button.
   - Here is what it should look like and please not the Additional Accounts tab which will have the email adress name without the domain. Please copy this for later: ![Image](UCSDSSHAccLookup.png)
   - **Important:** Reset the password to your ucsd email account beforehand and allow 10-15 minutes for this change to proccess before proceeding
   - Next: type in the following command to login:
   ```
   $ ssh < email address copied>@ieng6.ucsd.edu
   ```
   - You will then get this message and select yes to all of these messages
     > ⤇ ssh cs15lwi22zz@ieng6.ucsd.edu
     > The authenticity of host 'ieng6.ucsd.edu (128.54.70.227)' can't be established. RSA key fingerprint is SHA256:ksruYwhnYH+sySHnHAtLUHngrPEyZTDl/1x99wUQcec.Are you sure you want to continue connecting (yes/no/[fingerprint])?
   - You will then need to enter your password and should be connected.
## Trying Some Commands

   - Here is a list of commands that you might want to try on both your client and one the server. Please note difference in terminal output of the two as well.
     - > cd ~
     - > cd
     - > ls -a
     - > cp /home/linux/ieng6/cs15lwi22/public/hello.txt ~/
   - To logout you can use Ctrl-D or run the command exit

## Moving Files with scp:

- Here is a VS code screenshot with the directory listed

![Image](VSCodeLogin.png)
- The command to use in order to move this file (using the same email address without logging in) onto the server directory is:

```
scp WhereAmI.java cs15lwi22zz@ieng6.ucsd.edu:~/
```

- Next login and use the command > ls
- The server directory should then look like this:

 ![Image](VSCodeCopyingFile.png)

## Setting an SSH Key:

   - If you have not already, logout of the server and type in the command:

     ```
     ssh-keygen
     # on client (your computer)
     Generating public/private rsa key pair.
     Enter file in which to save the key (/Users/joe/.ssh/id_rsa): /Users/joe/.ssh/id_rsa
     Enter passphrase (empty for no passphrase):
     Enter same passphrase again:
     Your identification has been saved in /Users/joe/.ssh/id_rsa.
     Your public key has been saved in /Users/joe/.ssh/id_rsa.pub.
     The key fingerprint is:
     SHA256:jZaZH6fI8E2I1D35hnvGeBePQ4ELOf2Ge+G0XknoXp0 joe@Joes-Mac-mini.local
     The key's randomart image is:
     +---[RSA 3072]----+
     |                 |
     |       . . + .   |
     |      . . B o .  |
     |     . . B * +.. |
     |      o S = *.B. |
     |       = = O.*.*+|
     |        + * *.BE+|
     |           +.+.o |
     |             ..  |
     +----[SHA256]-----+

     ```

   - Continue to press return and your Key Should look something like this in the terminal

   - Then login and type the following commad and change the ucsd email accordingly and change users for your computer(should be seen in the screenshot above)
     ```
     $ ssh cs15lwi22zz@ieng6.ucsd.edu
     <Enter Password>
     $ mkdir .ssh
     $ <logout>
     $ scp /Users/joe/.ssh/id_rsa.pub cs15lwi22@ieng6.ucsd.edu:~/.ssh/authorized_keys
     ```

## Optimizing Remote Running
   - It is possible to run commands using quotes. It is also possible to run multiple commands at the same time with a ; before the first command. An example is the screenshot below:
   
   ![Image](VSCodeRunning2Commands.png)
