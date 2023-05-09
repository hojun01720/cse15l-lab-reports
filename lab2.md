# Lab 2<br/>

***Part 1:*** <br/><br/>
The image of my code: <br/>
![Code](https://github.com/hojun01720/cse15l-lab-reports/blob/main/Screenshot%202023-04-24%20112109.png?raw=true)<br/><br/>

The first use of '/add-message':<br/>
![First](https://github.com/hojun01720/cse15l-lab-reports/blob/main/Screenshot%202023-04-24%20111605.png?raw=true)<br/>

  1. After I run the code and added '/add-message?s=<String>' in the end of the URL, under the class Handler, the method handleRequest has received a new url.<br/>
  2. url.getPath().equals("/add-message") turns true, proceeding its if statement.<br/>
  3. String[] parameters = url.getQuery().split("=") divides "s=Who am I?" in to {"s", "Who am I?"}. <br/>
  4. Then parameters[0].equals("s") turns true proceeding its if statement. <br/>
  5. str += (parameters[1] + "\n"); "Who am I?\n" is saved into str and str is returned.<br/>
  6. The returned str is displayed on the server.<br/><br/>

  * If nothing is added after /, the server will display "Type '/add-message?s=<String>' in the end of current URL"
  * If other than s is typed after /add-message?, it will show "404 Not Found"<br/><br/>
  
The second use of '/add-message': <br/>
![Second](https://github.com/hojun01720/cse15l-lab-reports/blob/main/Screenshot%202023-04-24%20112255.png?raw=true)<br/>

   1. After I run the code and added '/add-message?s=<String>' in the end of the URL, under the class Handler, the method handleRequest has received a new url.<br/>
  2. url.getPath().equals("/add-message") turns true, proceeding its if statement.<br/>
  3. String[] parameters = url.getQuery().split("=") divides "s=24601!" in to {"s", "24601!"}. <br/>
  4. Then parameters[0].equals("s") turns true proceeding its if statement. <br/>
  5. str += (parameters[1] + "\n"); "24601!\n" is saved into str ***which "Who am I?/n" is already saved in*** and str is returned.<br/>
  6. The returned str is displayed on the server. <br/><br/>
  
   * If nothing is added after /, the server will display "Type '/add-message?s=<String>' in the end of current URL"
  * If other than s is typed after /add-message?, it will show "404 Not Found"<br/><br/><br/>
  
  
  ***Part 2:*** <br/><br/>
  
  Buggy code: <br/>
  
  ```
  static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = newArray[arr.length - i - 1];
    }
    return arr;
  }
  ```
<br/>

Failure input: <br/>
```
 public void testReversed2(){
    int[] input1 = {1,2,3,4,5};
    assertArrayEquals(new int[]{5,4,3,2,1}, ArrayExamples.reversed(input1));
  }
 ```
<br/> 

![Fail](https://github.com/hojun01720/cse15l-lab-reports/blob/main/Screenshot%202023-04-24%20134022.png?raw=true)<br/>

Working input: <br/>
```
 public void testReversed2(){
    int[] input1 = {0,0,0,0,0};
    assertArrayEquals(new int[]{0,0,0,0,0}, ArrayExamples.reversed(input1));
  }
 ```
<br/> 

![Work](https://github.com/hojun01720/cse15l-lab-reports/blob/main/Screenshot%202023-04-24%20134035.png?raw=true)<br/><br/>

The problem of the code is that the code that should've assign newArray[] using arr[] was actually assigned wrong way.<br/>
Wrong `arr[i] = newArray[arr.length - 1 - i]` <br/>
Correct `newArray[i] = arr[arr.length - 1 - i]` <br/><br/>

Then the full correct code will be: <br/>
```
 static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      newArray[i] = arr[arr.length - i - 1];
    }
    return newArray;
  }
```
<br/>

Now with this input, it will run correctly.
`int[] input1 = {0,0,0,0,0};` <br/>
![Fix](https://github.com/hojun01720/cse15l-lab-reports/blob/main/Screenshot%202023-04-24%20142150.png?raw=true)<br/><br/><br/>


***Part 3:***<br/>
I did not know at all how the create a local servers. Despite it is still confusing, and there are many things to understand like Server.java, it is quite thrilling I made a web server. Now I know some sense of using Server class and Handler things. I'll absolutely dive into it when I'm free.
