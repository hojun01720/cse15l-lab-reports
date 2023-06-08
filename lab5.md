# Lab 5<br/>
## Part 1 <br/>
Student: <br/><br/>

What environment are you using (computer, operating system, web browser, terminal/editor, and so on)? <br/>
* I use Windows OS with Visual Studio Code and its Git Bash terminal. <br/><br/>

Detail the symptom you're seeing. Be specific; include both what you're seeing and what you expected to see instead. Screenshots are great, copy-pasted terminal output is also great. Avoid saying “it doesn't work”. <br/>
* I do have a `ListExamples.java` file under `student-submission` directory, but the `grade.sh` is keep saying that it is not found. <br/>
![img](https://github.com/hojun01720/cse15l-lab-reports/blob/main/lab5pic1.png?raw=true) <br/>
Probably it is because the file is in the sub-directory of the `student-submission` directory, but I don't know what to change since the github url is given. <br/><br/>

Detail the failure-inducing input and context. That might mean any or all of the command you're running, a test case, command-line arguments, working directory, even the last few commands you ran. Do your best to provide as much context as you can. <br/>
* When I run `bash grade.sh <github_url>` with other url than this, they all seems to work well. URL like this `https://github.com/ucsd-cse15l-s23/list-methods-corrected` works. However this URL `https://github.com/ucsd-cse15l-s23/list-methods-nested` does not work. As I wrote up there, I don't know what to change since the URL is given. So PLEASE HELP ME. <br/><br/><br/>

TA: <br/><br/>
Yes as you've guessed `grade.sh` is the issue of the problem. Hence open the `grade.sh` and take a look at the code. <br/>
So the current issue is to find a `ListExamples.java` file in the directory. Find a line that has `ListExample.java` written. <br/>
Right now the directory of the `ListExamples.java` is hard coded. Hence, change it to look over all the sub-directories of `student-submission` directory. <br/>
(Hint: try `find` command!) <br/><br/><br/>

Student: I edited `grade.sh` file like this. <br/>
![img2](https://github.com/hojun01720/cse15l-lab-reports/blob/main/lab5pic3.png?raw=true) <br/>
I used `find` command to find `ListExamples.java` files that is under the `student-submission` directory or under its sub-directory. <br/>
Then when I ran the `nested` github url, it worked. <br/>
![img3](https://github.com/hojun01720/cse15l-lab-reports/blob/main/lab5pic4.png?raw=true) <br/>
Just in case, I also tried with the `corrected` github file to make sure this one still works, and it did. <br/>
![img4](https://github.com/hojun01720/cse15l-lab-reports/blob/main/lab5pic2.png?raw=true)<br/><br/>

They all seems to work now. <br/><br/><br/>

How I did: <br/>
1. I got this sep up done by just following the Skill Demo 2 tasks. <br/>
[Skill Demo 2 Tasks](https://edstem.org/us/courses/38707/discussion/3178565) <br/>
2. Then I ran `bash grade.sh` with this [corrected github URL](https://github.com/ucsd-cse15l-s23/list-methods-corrected) which shows to be working. <br/>
3. For not working github url, I used [nested github URL](https://github.com/ucsd-cse15l-s23/list-methods-nested) which initially fails the test when I run `bash grade.sh` with this URL. ***THIS WILL CAUSE THE BUG*** . <br/>
4. `grade.sh` before the change looks like this (line 8-22): <br/>
```
...
git clone $1 student-submission
echo 'Finished cloning'

if [[ -f student-submission/ListExamples.java ]]
then
  echo 'ListExamples.java found'
else
  echo 'ListExamples.java not found'
  echo 'Score: 0/4'
  exit 1
fi

cp student-submission/ListExamples.java ./grading-area

cp TestListExamples.java grading-area/
...
```
<br/>

`grade.sh` after the change looks like this: <br/>

```
...
echo 'Finished cloning'

direct="find student-submission/* -type f -name "ListExamples.java""

if [[ -f $($direct) ]]
then
  echo 'ListExamples.java found'
else
  echo 'ListExamples.java not found'
  echo 'Score: 0/4'
  exit 1
fi

cp $($direct) ./grading-area

cp TestListExamples.java grading-area/
...
```
<br/>

I added `direct="find student-submission/* -type f -name "ListExamples.java""` before `if` command and then replaced all the `student-submission/ListExamples.java` into `$($direct)` which the command is to find all the `ListExamples.java` under the `student-submission` directory including its sub-directories. <br/>

5. After fixing `grade.sh` file, when I run `bash grade.sh` with [nested github URL](https://github.com/ucsd-cse15l-s23/list-methods-nested), now it detects the `ListExamples.java` file and normally scores the test. <br/><br/><br/><br/>

## Part 2 <br/>
I learned a lot from the class. I learned how to use bash script and vim command. I was really surprised that I can save all the commands in the bash file and load it when it's necessary. This will be very helpful when I need to repeat the same commands over and over. <br/>
Also, I am happy to learn the vim. At first, I thought is is useless, but then I found out it is useful when I don't know where the file is to open up on VS Code, or when I am only working in the terminal. <br/>
These new skill will be very useful for further CSE classes and even at the workplace. I am gald that I learned them.
