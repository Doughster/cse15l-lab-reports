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
`pwd`
 
`mkdir`

`cd ~`

`cd`

`cp`

`ls`

`ls -lat`

![image](https://user-images.githubusercontent.com/97646041/149582806-c7af1ed4-4bb4-4dc1-8c67-a46af8bdd59d.png)


`ls -a`

![image](https://user-images.githubusercontent.com/97646041/149583049-3259ac39-2de8-4b04-bcfb-1d99741614f3.png)


`ls <directory>` (`<directory>` is `/home/linux/ieng6/cs15lwi22/cs15lwi22abc/` and `abc` is a members' username)

`cp /home/linux/ieng6/cs15lwi22/public/hello.text ~/`

`cat /home/linux/ieng6/cs15lwi22/public/hello.text`

**To log out of the server:**
Press `Ctrl + D` **or**
Type `exit`

![image](https://user-images.githubusercontent.com/97646041/149586269-8ae90417-bffb-41d4-abeb-25d62c2be48a.png)


---

## Step 4 - Moving Files with scp

- There is a command called `scp` that allows the user to copy files from their computer to a remote computer. 
- It is a nifty tool that will save a lot of time, but it can only be ran from the client, not the remote server. 
- First, you will want to create a file titled `WhereAmI.java` on your computer and put the following code into it:

```
class WhereAmI {
  public static void main(String[] args) {
    System.out.println(System.getProperty("os.name"));
    System.out.println(System.getProperty("user.name"));
    System.out.println(System.getProperty("user.home"));
    System.out.println(System.getProperty("user.dir"));
  }
}
```
- If you run `javac` and `java` on the terminal, the output should look something like this, depending on the operating system you are using: 

![image](https://user-images.githubusercontent.com/97646041/149589203-29a2905e-8850-4c9c-b265-581788a318d0.png)

- Then, in the same terminal, run this command, except with your username replaced:
 
 `scp WhereAmI.java cs15lwi22zz@ieng6.ucsd.edu:~/`

 - Enter your password when it requests for it.
 - Using ssh, log into ieng6 and there in the home directory, you should see the file. 

![image](https://user-images.githubusercontent.com/97646041/149590594-a7da3073-754d-476a-a35c-21d3e7d8a5d7.png)

- Through ssh, log into ieng6 again and use the command `ls` in the terminal. 
- You should see the file `WhereAmI.java` in the home directory.

![image](https://user-images.githubusercontent.com/97646041/149591004-173f8e21-aa6d-4892-ada7-9b700a05d926.png)

- Since the *server* has `java` installed, every user should be able to run the file no matter what. 

![image](https://user-images.githubusercontent.com/97646041/149591100-35600edf-ed08-4e48-93a7-dca289210cb2.png)

## Step 5 - Setting an SSH Key
- A program called `ssh-keygen` allows the user to use the `ssh` command to utilize a pair of files in place of your password.
- These `ssh` keys save the user the hassle of having to input their password each time they log in or run `scp`.
- To set up an `ssh` key, do this:

```
# on client (your computer)
$ ssh-keygen
Generating public/private rsa key pair.
Enter file in which to save the key (C:\Users\jeffr/.ssh/id_rsa): C:\Users\jeffr/.ssh/id_rsa
Enter passphrase (empty for no passphrase): 
Enter same passphrase again: 
Your identification has been saved in C:\Users\jeffr/.ssh/id_rsa
Your public key has been saved in C:\Users\jeffr/.ssh/id_rsa.pub.
The key fingerprint is:
SHA256:4B9K8HPEzC3Unpovh9OrBIt4imjAi+BYCuiccU6FKKc jeffr@DESKTOP-TGBDTC3
The key's randomart image is:
+---[RSA 3072]----+
|        ..       |
|       = ..      |
|  . o . *...     |
|.... = o .o      |
|+o  . * So       |
|Eo.+ o Bo.       |
|XoO o o o+       |
|=O +   .+ +      |
|+ .     .=..     |
+----[SHA256]-----+
```

- If your operating system is Windows, you will have to follow the extra `ssh-add` steps below: 

[Extra ssh-add Steps](https://docs.microsoft.com/en-us/windows-server/administration/openssh/openssh_keymanagement#user-key-generation)

![image](https://user-images.githubusercontent.com/97646041/149594024-479f6ac3-7e44-4de6-b40a-a2fe9a5213f2.png)

- We will now copy the *public* key to the `.ssh` directory of the user's account on the server by doing the following:

``` 
$ ssh cs15lwi22zz@ieng6.ucsd.edu
<Enter Password>
# now on server
$ mkdir .ssh
$ <logout>
# back on client
$ scp C:\Users\jeffr/.ssh/id_ed25519.pub cs15lwi22@ieng6.ucsd.edu:~/.ssh/authorized_keys
# You use your username and the path you saw in the command above
```

- After that step, you will no longer need to enter your password when you `ssh` or `scp` from the client to the remote server.

## Part 6 - Optimizing Remote Running 
- Put together all the commands and knowledge that you have learned, and try to come up with a process where you make a *local* edit to `WhereAmI.java`.
- Then copy that to the remote server and run the file. 
 
**Here are some steps to help you get started:**
- To run an `ssh` command directly on the remote server and then exit, you can write that command that you want to run in quotes at the end of the `ssh` command. 
- For example, this command will print the current working directory in the server and will exit immediately.

`$ ssh cs15lwi22zz@ieng6.ucsd.edu "pwd"`

![image](https://user-images.githubusercontent.com/97646041/149597066-4020951d-cb9b-446b-83e5-49da7bc9cfaf.png)


- You are able to run several commands on the same line in the majority of terminals by using semicolons in between the commands. 
- For example:

`$ cp WhereAmI.java OtherMain.java; javac OtherMain.java; java WhereAmI`

![image](https://user-images.githubusercontent.com/97646041/149597137-11799ff5-84a2-4b51-9dc2-939bc7f22130.png)


- Also, you can get the last command that was ran on your terminal by pressing the up-arrow on your keyboard. 

## If you couldn't figure it out, here is how to do it! ##
By implementing these shortcuts, we are capable of optimizing remote running by making changes to a file (in this case, `WhereAmI.java`), locally, and then copying and running it remotely.

- The first thing I did was to make some edits to `WhereAmI.java` locally. I changed it so that it would print out `Jeff` at the end of the other print statements.
- Next, I used the `up arrow` twice and pressed `enter` in the terminal **(three keytrokes)**, which basically let me secure copy (**scp**) over the changes of WhereAmI.java onto the remote server
- The final step was to use the `up arrow` twice and `enter` again **(three keystrokes)**, which resulted in me being able to `ssh` and execute both the `javac` and `java` commands remotely in one line because I used a semicolon to run several commands on one line.
- The image below shows the commands that I ran on the server and how the file changes were successfully copied from the local client, onto the remote server.
- I used **six keystrokes** in total.
![image](https://user-images.githubusercontent.com/97646041/152279364-fd6f5b35-e297-4fa6-bc94-165837f9b6df.png)


**Overall, many establishments and CS courses employ the usage of course-specific accounts, so learning how to use it to your advantage will be optimal for you and your future jobs.**
