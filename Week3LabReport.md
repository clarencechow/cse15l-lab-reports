# Part 1

My code for the `StringServer` web server:  
```
import java.io.IOException;
import java.net.URI;

class StringHandler implements URLHandler {

    String s = "";

    public String handleRequest(URI url) {
        if(url.getPath().equals("/add-message")) {
            String[] parameters = url.getQuery().split("=");
            if(parameters[0].equals("s")) {
                s += parameters[1] + "\n";
                return s;
            } else
                return "404 not found";
        }
        return "404 not found";
    }
}

class StringServer {
    public static void main(String[] args) throws IOException {
        if(args.length == 0){
            System.out.println("Missing port number! Try any number between 1024 to 49151");
            return;
        }

        int port = Integer.parseInt(args[0]);

        Server.start(port, new StringHandler());
    }
}  
```

![Image](https://github.com/clarencechow/cse15l-lab-reports/blob/main/addMessage.png?raw=true)  
In this screenshot the method `handleRequest` is called with the argument `http://localhost:4000/add-message?s=how%20was%20your%20day`.
Since the path of the URL is "add-message", the call to `url.getPath().equals("/add-message")` will return `true` and the program will continue through the first if-statement.
`url.getquery()` is called to retrieve the part of the URL after the "?", and `.split("=")` converts the query into an array of strings that were seperated by the 
delimiter "=". These strings are `"s"` and `"how was your day"`. Because the first string is `"s"`, `parameters[0].equals("s")` will return `true` and `"how was your day\n"`
will be added to the string `s`, which at this point already contained `"Hello\nhow are you\n"`. Afterwards, `handleRequest` returns `s`, which is now `"Hello\nhow are you\nhow was your day\n"`

![Image](https://github.com/clarencechow/cse15l-lab-reports/blob/main/404.png?raw=true)  

In this screenshot the method `handleRequest` is called with the argument `http://localhost:4000/add`. Since the path of the URL is not "add-message",
the call to `url.getPath().equals("/add-message")` will return `false` and the program will return `"404 not found"`. `s` remains unchanged from this method call.

# Part 2

Chosen bug is the `reserved` method from `ArrayExamples.java`.  
Failing test:
```
    @Test
    public void testReversed3Elements() {
        int[] input1 = {10, 20, 30};
        assertArrayEquals(new int[]{30, 20, 10}, ArrayExamples.reversed(input1));
    }
```
Passing test:
```
    @Test
    public void testReversedAll0() {
      int[] input1 = {0, 0, 0, 0};
      assertArrayEquals(new int[]{0, 0, 0, 0}, ArrayExamples.reversed(input1));
    }
```
![Image](https://github.com/clarencechow/cse15l-lab-reports/blob/main/testrunning.png?raw=true)  
(Running tests in VS Code)  
Output for failing test: 
```
arrays first differed at element [0]; expected:[30] but was:[0]
 at ArrayTests.testReversed3Elements(ArrayTests.java:22)
Caused by: java.lang.AssertionError: expected:[30] but was:[0]
```
To fix the bug, I had to switch some areas that used `newArray` instead of `arr` and vice versa  
Before:
```
static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = newArray[arr.length - i - 1];
    }
    return arr;
 }
```
After:
```
static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      newArray[i] = arr[arr.length - i - 1];
    }
    return newArray;
 }
```
This change fixes the issue because before the fix, the code was replacing the values of the argument array with those of the newly created array in reverse order.
This made the values of the original array, which was returned, all equal 0. The new code instead replaces the values of the new array with those of the old
array in reverse order, and returns the new array afterwards. This is what the method is expected to do.

# Part 3

One thing I learned from this lab was the `File` class in Java. After reading through the documentation on https://docs.oracle.com/javase/8/docs/api/java/io/File.html,
 I learned that the `File` class is used to represent a file or directory path, and can be used to get a lot of useful information on files, such as their size or when
 it was last modified.

