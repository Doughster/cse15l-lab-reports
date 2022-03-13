# Lab Report Five #

## How the Tests were Found with Different Results: ##
**In order to find the different test results:**

- Using a bash script, I printed the different results onto a results text file for both parsers.
- I compared the results of each markdown parser using `diff`.
- Finally, I picked the tests that had different test results .

## Test One ##
`567.md`
 ```
 [foo](not a link)
  
 [foo]: /url
 ```
 
**My Result:**

`[not a link]`

**Parser Result:**

`[] <-- (expected/actual result!)`

- Since the test file does not have the typical extensions that a link would have, like `.html` or `.md`, it should not contain
any links. 
- Therefore, I believe that the result from parser is actually correct and that my result is incorrect

**My Code**

![image](https://user-images.githubusercontent.com/97646041/158083669-9a2aeeff-2642-42e5-bb88-0778ab89501c.png)
- This piece of code does not work for actual links.
- We can fix this by adding an additional piece of code that checks each link if they have an extension like `.md` or `.html`.
- This check would include checking the substring from `openParen + 1` to the `closeParen`, and then spliting each individual link by commas.

## Test Two ##
`579.md`

`![foo](<url>)`
 
**My Result:**

`[<url>]`

**Parser Result:**

`[<url>]`

- For this test file, I believe that both parsers are incorrect.
- This is because in `579.md`, the code isn't a link. It is an image as seen by the exclamation mark.
- As a result, it shouldn't print a link when it is an image.

**My Code**

![image](https://user-images.githubusercontent.com/97646041/158083669-9a2aeeff-2642-42e5-bb88-0778ab89501c.png)
- The code above does not check if there is an exclamation point at the beginning at the string.
- Therefore, it does not check for images in the string.
- We can fix this issue by checking if the first character in the string is an exclamation point.
- If it does start with `!`, we can ignore it. Else, we can continue to parse it.

