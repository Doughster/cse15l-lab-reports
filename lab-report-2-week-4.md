# Week 4 Lab Report 2: Tests Symptoms and Bugs #
## First Test Implementation ##

**Screenshot of the code change diff from Github:**
![image](https://user-images.githubusercontent.com/97646041/151636751-e672b446-b7a1-4299-aa6f-aa4d04f71c37.png)


**Link to the test file for a failure-inducing input:**

[Test File with Error (Link)](https://github.com/Doughster/markdown-parse/commit/20e6ce31df65b4a398590f1e15d385dd5569867a)

**Symptom/output of failure-inducing input:**

![image](https://user-images.githubusercontent.com/97646041/151634542-e56e1556-4c9a-4628-bdd1-221fd97b4d0d.png)

**How to fix the bug**
The test file has a pair of parentheses within the parentheses for the link, so that is why there is an error that causes a loop to print. To semi-fix this problem, I did this:

![image](https://user-images.githubusercontent.com/97646041/151635143-94ce1ed8-90ca-479f-bae9-b5c7cf095b95.png)



**Relationship between the bug, the symptom, and the failure-inducing input:**

For the first test implementation, the **symptoms** of the **failure-inducing input** exposed the **bug** within the code for *MarkdownParse.java.*

Therefore, the only way to examine if there is an error with the code created is to create a possible edge case in which the user tries to make a 
failure-inducing input to reveal any bugs lying within the code.

In this situation, we created a possible edge case **(parentheses within the link)** that caused a failure-inducing input **(continuous loop of 42)**, and that input
exposed a bug in the code that was created in *MarkdownParse.java*.

## Second Test Implementation ##


**Screenshot of the code change diff from Github:**
![image](https://user-images.githubusercontent.com/97646041/151636755-8b973e49-b0c0-4ac5-8194-3989295f0acf.png)


**Link to the test file for a failure-inducing input:**

[Test File with Error (Link)](https://github.com/Doughster/markdown-parse/commit/d5bf8446ebdd46e56890fa4962a854b321aff29c)

**Symptom/output of failure-inducing input:**

![image](https://user-images.githubusercontent.com/97646041/151635517-d297d59d-c5c6-42af-8c16-274380698082.png)

**How to fix the bug**

The test file has a a pair of brackets, but not a pair of parentheses, so it creates a `StringIndexOutOfBoundsException`. To fix this problem, I did this:

![image](https://user-images.githubusercontent.com/97646041/151636263-7b2579b6-0375-4bf4-bc06-916eafb49d16.png)



**Relationship between the bug, the symptom, and the failure-inducing input:**

In this situation, we created a possible edge case **(a link with no paratheses)** that caused a failure-inducing input **(a _StringIndexOutOfBoundsException_)**, and that input
exposed a bug in the code that was created in *MarkdownParse.java*. The file expected paratheses within the file and when it could not find them, it created an exception. Therefore, 
the code doesn't take into account what to do if there are no paratheses in the file, which is considered a bug.

## Third Test Implementation ##


**Screenshot of the code change diff from Github:**
![image](https://user-images.githubusercontent.com/97646041/151636915-ad818cfb-cea8-426b-9afd-e3a9f79d6898.png)


**Link to the test file for a failure-inducing input:**

[Test File with Error (Link)](https://github.com/Doughster/markdown-parse/commit/610b29a5effb3fee64a4853b9067e603df94db84)

**Symptom/output of failure-inducing input:**

![image](https://user-images.githubusercontent.com/97646041/151637100-753bec25-e241-49e6-b69d-25284566ab7a.png)

**How to fix the bug**

The output stated that we had to catch or declare an IOException. It took us a while to find out what this meant, but we finally figured it out and added this piece of code:

![image](https://user-images.githubusercontent.com/97646041/151637275-13dee627-d413-4dd7-bdfe-240a07ab92a0.png)



**Relationship between the bug, the symptom, and the failure-inducing input:**

In this situation, the symptom of the bug were the error messages we stating that there was an unreported exception IOException and that it was necessary to catch or declare it.
There wasn't really a failure-inducing input because it was more of a user mistake that we forgot to throw an I/O Exception for the method. It was only until we got the symptom (error message),
that we realized there was a bug within our method call.

