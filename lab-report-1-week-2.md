# Lab Report 1

## Step 1 - Installing VScode
- First, you will need to download Visual Studio Code, which is a source-code editor that supports desktops for Windows, Linux, 
and macOS. 
- Click on the link for the website: [Visual Studio Code](https://code.visualstudio.com/), 
- Follow the instructions to download the platform the best supports your device.   

![image](https://user-images.githubusercontent.com/97646041/149450264-811437ec-c696-47fd-99eb-125d8a5ffefb.png)

**After installing the editor, it should look something remotely like this:**

![image](https://user-images.githubusercontent.com/97646041/149451401-701cce99-1cb9-4df2-bf17-56c8f0d60642.png)

## Step 2 - Remotely Connecting 
- If your computer is supported by Windows, it is necessary to install OpenSSH, which is a program that is capable of connecting your computer
to other computers that share the same type of account. 
- Here is the link to help you get started: [Open SSH Installation](https://docs.microsoft.com/en-us/windows-server/administration/openssh/openssh_install_firstuse) 
- When you have finishing installing OpenSSH, you will then have to search for your special account that can only be identified with CSE 15L, 
which can be searched up by following the instructions on this website: [CSE 15L Account](https://sdacs.ucsd.edu/~icc/index.php)
- After you have find your account, you will be following the instructions in ["Connect to a remote host"](https://code.visualstudio.com/docs/remote/ssh#_connect-to-a-remote-host) step.
- Connect to the server by opening a fresh terminal and put in the following command except with the `zz` replaced by the two letters are identified with your specific account. 

`$ ssh cs15lwi22zz@ieng6.ucsd.edu`

- You may get a request that asks for your fingerprint. 
- It is recommended that you say yes to this request.
- After you say yes and enter your password, you should get a message that looks similar to this:

![image](https://user-images.githubusercontent.com/97646041/149467878-c3d57109-9a8c-4e85-a900-d5cd66a59810.png)

**If this message appears, you have sucessfully connected your terminal to a computer in the CSE basement.**

## Step 3 - Trying Some Commands
- There are several commands that you will be implementing in this course. 
- Here are some important ones:
---
`cd ~`

`cd`

`ls -lat`

`ls -a`

`ls <directory>` (`<directory>` is `/home/linux/ieng6/cs15lwi22/cs15lwi22abc/` and `abc` is a members' username)

`cp /home/linux/ieng6/cs15lwi22/public/hello.text ~/`

`cat /home/linux/ieng6/cs15lwi22/public/hello.text`

**To log out of the server, do this:**
Press `Ctrl + D` **or**
Type `exit`

---

## Step 4 - 


