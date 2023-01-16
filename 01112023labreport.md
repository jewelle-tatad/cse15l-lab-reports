# **01.11.2023 Lab Report: Remote Access**
This tutorial will cover the following:
- Visual Studio Code Setup
- Remotely Connecting to a Server
- Trying Out Some Commands

## **Visual Studio Code Setup**
In order to access the remote server, I used the git bash terminal in Visual Studio Code (VSCode).

To setup, download [Visual Studio Code](https://code.visualstudio.com/) for your operating system (I'm currently using Windows) and follow the instructions on the website. You will also need to download [git](https://gitforwindows.org/) for your operating system (This link is for git for Windows) in order to access the git bash terminal.

Once you open up VSCode, your window should look similar to this:

![Screenshot_20230115_113715](https://user-images.githubusercontent.com/122484428/212623172-b2271d2a-6a04-41ab-b7a9-0a5ea300f973.png)

To access bash, click on Terminal in the top  menu bar and select New Terminal. You can also access this via Ctrl+Shift+`.

![Screenshot_20230115_114143](https://user-images.githubusercontent.com/122484428/212623493-2ba92e92-1a2b-449f-b862-640e5f0d2cf6.png)

After opening up the terminal, make sure it is set to bash in order to use the Git Bash terminal. Your terminal should look something like this.

![Screenshot_20230115_114518](https://user-images.githubusercontent.com/122484428/212624071-8840a997-f05b-4553-bf2e-997fe15827a0.png)

## **Remotely Connecting to a Server**
You are now ready to remotely connect to a server! I will be connecting to the ieng6 server in order to access my CSE 15L course account.

In order to do so, I will need a couple of pieces of information, such as my password and the account name of my CSE 15L account. Assuming you are a UCSD student, you will be able to find your account information [here](https://sdacs.ucsd.edu/~icc/index.php). You may need to reset your password to access your account, which may take up to 10 minutes to take effect.

Once you have access to your account information, type the following command into the terminal:

```
$ ssh [account information]
```
For example, if I were to access my CSE 15L account, I would type the following command into the terminal:

```
$ ssh cs15lwi23aba@ieng6.ucsd.edu
```

![Screenshot_20230116_120521](https://user-images.githubusercontent.com/122484428/212628173-5c5877d9-ae47-41db-bb1f-de361b53bec2.png)

An error that occurred during lab that may occur to you was that the remote server would refuse to connect and close the connection after a short period of time. This happened to me a couple of times and was rectified by either following bash's prompt to reinstall an extension, resetting VSCode, or by resetting the entire device altogether.

If it is your first time accessing a server, a prompt may show up to ask you to continue to connect to a server. If you decide to continue connecting, you will be prompted to put your password in.

![Screenshot_20230115_115548](https://user-images.githubusercontent.com/122484428/212626182-511a379a-4fdc-4675-91f0-bee5d0be08cb.png)

In my case, you will not be able to see your password as you are putting it in, and you will be prompted to reenter your password if you mess up. After a certain number of times, you will be kicked off of the server and timed out for a short period of time if you keep messing up.

Once you have entered your password correctly, the following shows up:

![Screenshot_20230116_120326](https://user-images.githubusercontent.com/122484428/212627214-67381164-ed6a-4035-a2af-95ebd4891682.png)
![Screenshot_20230115_115603](https://user-images.githubusercontent.com/122484428/212626518-ccdc618e-73a0-4513-a81d-5a50feb67824.png)

This message shows a couple of things, such as your last login time (if you've accessed this server before), the number of users in a cluster, how much load you are currently using, and the hostname of the computer you're currently connected to. A notice also pops up, though this may vary from user to user.

## **Trying Out Some Commands**
Now that you've connected to the remote server, you are ready to start trying out some commands! Here are some commands I tried out and what their outputs were, as well as explanations of what these commands are.

**`$ cat` prints the contents of file/files given by a path.**

```
$ cat /home/linux/ieng6/cs15lwi23/public/hello.txt
Hello! Welcome to CSE 15L
```

**If not given a file, it will send back an error.**

```
$ cat /home/linux/ieng6/cs15lwi23  
cat: /home/linux/ieng6/cs15lwi23: Is a directory
```

**`$ ls` lists files and folders in a given path.**
```
$ ls /home/linux/ieng6/cs15lwi23/public
README.class README.instructor bin broadcast broadcastsh modulefiles
```

```
$ ls -lat
total 128
-rwxr-x---   1 cs15lwi23aba ieng6_cs15lwi23    26 Jan 16 00:10 hello.txt
drwxr-s---   6 cs15lwi23aba ieng6_cs15lwi23  4096 Jan 16 00:10 .
-rw-r--r--   1 cs15lwi23aba ieng6_cs15lwi23  1329 Jan 15 23:55 .modulesbegenv
-rw-r-----   1 cs15lwi23aba ieng6_cs15lwi23     0 Jan 15 23:55 .motd
drwxr-sr-x 638 cs15lwi23    ieng6_cs15lwi23 53248 Jan 13 08:06 ..
-rw-------   1 cs15lwi23aba ieng6_cs15lwi23   422 Jan 11 12:36 .bash_history
drwxr-sr-x   2 cs15lwi23aba ieng6_cs15lwi23  4096 Jan 11 11:35 perl5
drwxr-sr-x   3 cs15lwi23aba ieng6_cs15lwi23  4096 Jan 11 11:35 .local
drwxr-sr-x   3 cs15lwi23aba ieng6_cs15lwi23  4096 Jan 11 11:35 .config
drwxr-sr-x   3 cs15lwi23aba ieng6_cs15lwi23  4096 Jan 11 11:35 .cache
-rwxr-x---   1 cs15lwi23aba ieng6_cs15lwi23   290 Jan  6 15:09 .zshrc
-rwxr-x---   1 cs15lwi23aba ieng6_cs15lwi23   481 Jan  6 15:09 .zshenv
-rwxr-x---   1 cs15lwi23aba ieng6_cs15lwi23  1931 Jan  6 15:09 .zprofile
-rwxr-x---   1 cs15lwi23aba ieng6_cs15lwi23  1961 Jan  6 15:09 .profile
-rwxr-x---   1 cs15lwi23aba ieng6_cs15lwi23   837 Jan  6 15:09 .procmailrc
-rwxr-x---   1 cs15lwi23aba ieng6_cs15lwi23   431 Jan  6 15:09 .login
-rwxr-x---   1 cs15lwi23aba ieng6_cs15lwi23   155 Jan  6 15:09 .locallogin
-rwxr-x---   1 cs15lwi23aba ieng6_cs15lwi23  1692 Jan  6 15:09 .kshrc
-rwxr-x---   1 cs15lwi23aba ieng6_cs15lwi23  1931 Jan  6 15:09 .cshrc
-rwxr-x---   1 cs15lwi23aba ieng6_cs15lwi23  1721 Jan  6 15:09 .bashrc
-rwxr-x---   1 cs15lwi23aba ieng6_cs15lwi23   975 Jan  6 15:09 .bash_profile
```
The following commands returned nothing:

**`$ cd` is used to change the current working directory to another path.**

```
$ cd
$ cd ~
```

**`$ cp` copies a file to a directory.**

```
$ cp /home/linux/ieng6/cs15lwi23/public/hello.txt ~/
```

To close the connection to the remote server, use the shortcut Ctrl+D. The following should pop up and you should be disconnected from the server.

![image](https://user-images.githubusercontent.com/122484428/212631553-6b070814-9cb3-4a83-8c14-18a5e5601195.png)
