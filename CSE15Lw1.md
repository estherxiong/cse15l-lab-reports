# Week 1 Lab Report

## Step 1: Installing VScode

* Go to the Visual Studio Code website https://code.visualstudio.com/, and follow the instructions to download and install it on your computer.
* When installed, you should open a window that looks like this:
<img width="1440" alt="firststep" src="https://user-images.githubusercontent.com/122568591/212244337-3b98a923-50f7-4fa3-9955-59f184b2155e.png">

## Step 2: Remotely Connecting

* There is a first step to do when you're on Windows: install `git` for Windows.

  [Git for Windows](http://a.com)
* Once installed, use the steps in this post to set default terminal to use the newly-installed `git bash` in Visual Studio Code:
* 
  [Using Bash on Windows in VScode](http://a.com)
  
* Then, to use ssh, open a terminal in VScode. (Terminal → New Terminal menu option). Your command will look like this, but with the zz replaced by the letters in your course-specific account.

```$ ssh cs15lwi23zz@ieng6.ucsd.edu```
  
* If it's your first time connected to the server, then you will get this message:

 ```⤇ ssh cs15lwi23zz@ieng6.ucsd.edu
The authenticity of host 'ieng6.ucsd.edu (128.54.70.227)' can't be established.
RSA key fingerprint is SHA256:ksruYwhnYH+sySHnHAtLUHngrPEyZTDl/1x99wUQcec.
Are you sure you want to continue connecting (yes/no/[fingerprint])? 
```
* Type yes and press enter, then give your password; the whole interaction should look something like this once you give your password and are logged in:

```# On your client
⤇ ssh cs15lwi23zz@ieng6.ucsd.edu
The authenticity of host 'ieng6-202.ucsd.edu (128.54.70.227)' can't be established.
RSA key fingerprint is SHA256:ksruYwhnYH+sySHnHAtLUHngrPEyZTDl/1x99wUQcec.
Are you sure you want to continue connecting (yes/no/[fingerprint])? 
Password: 
```
<img width="392" alt="Screenshot 2023-01-12 at 9 21 01 PM" src="https://user-images.githubusercontent.com/122568591/212245397-7685ba70-c096-4f75-93ec-1199af418c14.png">


## Step 3: Trying Some Commands
* Try running the commands cd, ls, pwd, mkdir, and cp a few times in different ways.

Here are some commands that are useful:

- `cd ~`
- `cd`
- `ls -lat`
- `ls -a`
- `ls <directory> where <directory>` is `/home/linux/ieng6/cs15lwi23/cs15lwi23abc`, where the abc is one of the other group members’ username
- `cp /home/linux/ieng6/cs15lwi23/public/hello.txt ~/`
- `cat /home/linux/ieng6/cs15lwi23/public/hello.txt`
<img width="597" alt="Screenshot 2023-01-12 at 9 23 49 PM" src="https://user-images.githubusercontent.com/122568591/212245645-1160f8d9-1fcd-4489-8e83-03d550a011b8.png">

Hint: use `Ctrl-D1` and run the command `exit` to log out of the remote server.
