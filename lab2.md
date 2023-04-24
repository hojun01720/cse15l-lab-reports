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
