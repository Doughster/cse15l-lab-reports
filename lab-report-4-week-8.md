# Lab Report Six #
**My Markdown-parse Repository:** https://github.com/Doughster/markdown-parse

**Markdown-parse Repository I Reviewed:** https://github.com/TheZenMasterz/markdown-parse
## Snippet One ## 
**This snippet used for this test:**

``` 
'[a link'](url.com)

[another link](`google.com)`

[`cod[e`](google.com)

[`code]`](ucsd.edu)
```
**The test for this snippet:**

![image](https://user-images.githubusercontent.com/97646041/155803936-0bd25f39-4879-48a3-a1ce-09947c8eac8d.png)

## **Results For My Implementation:** ##
**The test did not pass**
![image](https://user-images.githubusercontent.com/97646041/155803547-3c95a36d-b2a1-4f9e-b9b2-0495a5e0fafa.png)


## **Results For The Implementation I Reviewed:** ##
**The test did not pass**
![image](https://user-images.githubusercontent.com/97646041/155805243-40c93a6a-ce8c-411f-91da-fd571387f8c3.png)


## Snippet Two ## 
**This snippet used for this test:**
``` 
[a [nested link](a.com)](b.com)

[a nested parenthesized url](a.com(()))

[some escaped \[ brackets \]](example.com)
```

**The test for this snippet:**

![image](https://user-images.githubusercontent.com/97646041/155804895-1fdf7d03-b189-41f0-bde0-b9e75be26322.png)

## **Results For My Implementation:** ##
**The test did not pass**
![image](https://user-images.githubusercontent.com/97646041/155803867-a8b60f31-97f0-42ee-9bc7-ecf46c9fcaba.png)


## **Results For The Implementation I Reviewed:** ##
**The test did not pass**
![image](https://user-images.githubusercontent.com/97646041/155805625-a856ef04-009d-4c55-81e1-46592f162e40.png)


## Snippet Three ## 
**This snippet used for this test:**
``` 
[this title text is really long and takes up more than 
one line
and has some line breaks](
    https://www.twitter.com
)
[this title text is really long and takes up more than 
one line](
    https://ucsd-cse15l-w22.github.io/
)
[this link doesn't have a closing parenthesis](github.com
And there's still some more text after that.
[this link doesn't have a closing parenthesis for a while](https://cse.ucsd.edu/
)
And then there's more text
```

**The test for this snippet:**

![image](https://user-images.githubusercontent.com/97646041/155804786-7530cd89-d6e9-4a2d-a6e0-81100b177dcd.png)

##  **Results For My Implementation:** ## 
**The test did not pass**
![image](https://user-images.githubusercontent.com/97646041/155804699-a2933706-d3ab-4cce-b10d-af024f52fbcd.png)


## **Results For The Implementation I Reviewed:** ##
**The test did not pass**
![image](https://user-images.githubusercontent.com/97646041/155805971-62056947-e5c4-41ab-9aa1-de8a7841c74c.png)

# Questions For the Snippets #

## Snippet One Question ##
For **Snippet One**, I do believe that there is a small code change that will make my program work for **Snippet One** and all related
cases that use inline code with backticks. This code change would look through the code for backticks in the file, and then they would
avoid them. With this piece of code change, backticks would be avoided even if they existed in the file, and `MarkdownParse.java` would not
insert them into the tests for `MarkdownParseTest.java`.

## Snippet Two Question ##
For **Snippet Two**, I do believe that there is a small code change that will make my program work for **Snippet Two** and all related cases
that nest paraentheses, brackets, and escaped brackets. This code change would include all of the characters between the opening symbol (i.e. brackets,
parentheses, etc.) and the ending symbol (i.e. brackets, parentheses, etc.). By incorporating this change of code, the `getLinks` method 
gets all of the characters in the link. For example, if I were to incorporate this code, **Snippet Two** would have an output of `a.com(())` instead of
`a.com((`.

## Snippet Three Question ##
For **Snippet Three**, I do not believe that there is a small code change that will make my program work for **Snippet Three** and all related
cases that have newlines in brackets and parentheses. This is due to the fact that the method will have to read through more code and skip through more
backticks, which is a change I incorporated in my change for **Snippet One**. Furthermore, my change for **Snippet Two** will include all of the code
between the opening symbol and ending symbol in the code. There may also be more new lines of code changes that I have to incorporate to make sure that
the tests and outputs for **Snippet Three** pass and are correct. 


