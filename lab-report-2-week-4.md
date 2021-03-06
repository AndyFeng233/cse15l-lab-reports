# Lab report 2 (week 4)

## Purpose: Change the codes to improve program 

## Screenshot of the code change different from Github
![image](changecode.png)
These are the changes that I made to improve the program. 

## Links to the failure-inducing test files
To test the program, I created four different test files.
1. Originally, the test file has a few empty lines at the end of the test file, which causes the program to crush. After deleting the empty lines, the program gives the correct outputs. Basically, the file tests if the program will run and return an  expected output of link. [Failure-inducingTestFiles](https://github.com/AndyFeng233/markdown-parser/blob/main/test-file.md)

2. The test file is going to test if the program will return multiple expected link without returning the flaw ones. [TestMultipleLink](https://github.com/AndyFeng233/markdown-parser/blob/main/test-file1.md)

3. The test file checks if the program will return the unexpected link as an output. [TestSingleFlawLink](https://github.com/AndyFeng233/markdown-parser/blob/main/testfile2.md)

4. The test file aims to test if the program will return the image link. [ImageTest](https://github.com/AndyFeng233/markdown-parser/blob/main/testImage.md)

## Show the symptom of that failure-inducing input by showing the output of running the file at the command line for the version where it was failing

1. The failure-inducing input is a website link without correct format. The failure-inducing input is shown below ![image](incorrectFormat.png). The sympton is the out-of-bound error, which is not what we expect to happen.The symptom is shown below. ![image](outOfBound%20.png) In order to fix the bug, I write ` if(markdown.indexOf("[") == -1 || markdown.indexOf("]") == -1 || markdown.indexOf("(") == -1 || markdown.indexOf(")") == -1 ||markdown.indexOf("!") != -1) {
                return toReturn;
            }`.

2. The failure-inducing input is a list of links mixed with correct format of links and incorrect format of links. The input is shown below. ![image](ListOfLink.png). The symptom is the return of links that contain both expected and unexpected link. The symptom is shown below. ![image](ListLinkError.png). However, I am still working on fixing the bug that leads to this symptom.

3. The failure-inducing input is a link to the image which has **!** in front of the **[**. The image link is shown below ![image](image.png). The symptom is the return of the image link, which is not what we expect. The screenshot of the symptom is shown below. ![iamge](testi.png). In order to fix the bug that causes the symptom, I write `else if(markdown.indexOf("!") != -1) {
                return toReturn;
            }`.



## Relationship between the bug, the symptom, and the failure-inducing input

  **Bug** is a flaw in the coding which can cause none or multiple symptoms. **Symptom** is the defected problem that we can see in the terminal, such as wrong output and infinite loop. The **failure-inducing output** aims to trigger the bugs in the codes to produce symptoms. 

 1. In the test-file.md, the failure-inducing input is the empty lines at the very end. Those few empty lines trigger the bug in the code. To be more specific, the code fails in its function when reading the empty lines at the end of the files. The failure in code leads to the symptom of compile error. 

 2. In the test-file1.md, the failure-inducing input is a list of normal website links in correct format mixed with some website links in incorrect format. The bug in code is the failure in recognizing and removing the links in incorrect format. The symptom is the wrong output which prints out the links in incorrect format as well. 

 3. In the testfile2.md, the failure-inducing input is a single link in incorrect format. The bug in code fails to recognizing and removing the unexpected link. The symptom is the wrong output which prints out the unexpected link. 

 4. In the testImage.md, the failure-inducing input is a image link. The input will trigger the bug in the code which fails to recognize and removing the unexpected image link. The bug in the code causes the symptom of printing out the unexpected link. 