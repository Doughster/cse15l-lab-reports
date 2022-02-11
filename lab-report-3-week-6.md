# Group Choice Three - Copying Whole Directories With `scp -r` #

## Screenshot of copying the whole markdown-parse directory onto my ieng6 account ## 
- I coped the whole markdown-parse directory by typing `$ scp -r . cs15lwi22@ieng6.ucsd.edu:~/markdown-parse` into the command line
- The command `scp` is worked recursively by the command `-r `
- The source is `.` and is the current directory
-  `scp` makes the `markdown-parse` directory on the remote server from the command `~/markdown-parse`, and then it copies the contents of the directory recursively there

![image](https://user-images.githubusercontent.com/97646041/153680085-177bafa7-5bc4-4dc3-94ad-1b628b9a1dcc.png)
![image](https://user-images.githubusercontent.com/97646041/153680124-73e71edd-6173-4ea2-9745-d0adda7b2eff.png)
![image](https://user-images.githubusercontent.com/97646041/153680159-af33db1f-137e-43fc-b438-c4afe0de6b75.png)
![image](https://user-images.githubusercontent.com/97646041/153680183-d257438f-0a46-42ed-9b84-bf8f8fad9d3e.png)

## Logging onto my ieng6 account and compiling and running all five tests for my repository ##
- I logged onto my ieng6 account by typing `ssh cs15lwi22zz@ieng6.ucsd.edu` into the commmand line
- I then ran and compiled the five test files for my repository by using the `javac` and `java` commands

![image](https://user-images.githubusercontent.com/97646041/153680774-dcb8eb84-f50d-46b7-95c3-3d7f60b64277.png)

## Combining `scp`, `;`, and `ssh` to copy the whole directory and compile and run the tests in one command line ##
- I used `scp MarkdownParse.java cs15lwi22zz@ieng6.ucsd.edu:~/; javac MarkdownParse.java; java MarkdownParse test-file.md` to run and compile the five test files on the remote server
- I was able to copy the whole direct and run all of the tests in one command line
![image](https://user-images.githubusercontent.com/97646041/153681440-bb1ad1ae-6741-4a52-8a99-f1c79134e48b.png)

